# CHIMERA benign behaviour dataset

Behaviour records of **benign** programs run in the CHIMERA sandbox (DRAKVUF on Xen), for
training and checking the classifier. Every record is one run of one program inside a
Windows or Linux guest. The programs themselves are **not** in this repository: it holds
only what the sandbox observed.

The data is pushed while the batch runs, so counts grow over time. `summary.json` and
`report.md` always describe the latest push.

## Layout

```
windows/benign/<sha256>/<arm>-<run>/features.json        what the program did (classifier input)
                                    labels.json          run record and ground-truth label
                                    classification.json  verdict of the model running at the time
linux/benign/<sha256>/<arm>-<run>/...                     same three files for Linux runs
index.csv       one row per run (start here)
programs.csv    one row per program: name, version, category, source, how it was started
runs.csv        one row per run from the sandbox's own run log (timings, counters)
summary.json    batch summary (counts by status, arm, OS)
report.md       human-readable batch report
evidence/earlier/  summary.json + report.md of the earlier batch
evidence/v3/       summary.json + report.md of the current batch
test-set/       reserved for held-out malware runs (empty for now)
```

`<sha256>` is the SHA-256 of the file that was submitted. `<arm>-<run>` is the sandbox
configuration and run number, for example `H3-1` or `L-1`.

## How the runs were made

| | Windows | Linux |
|---|---|---|
| Guest | Windows 10 x64 | Debian 12 x86-64 |
| Arm | `H3`: hardened guest with host firmware IDs, everyday user apps installed, simulated mouse input, hidden hypervisor CPUID | `L` (one image, no arms) |
| Timeout | 180 s | 180 s |
| Runs per program | 1 | 1 |
| Network | contained: DNS and HTTP(S) answered by INetSim, no internet access | same |

- Current batch (`batch = v3`): one run per program, so the variety comes from many
  distinct programs, not from repeats.
- The containment check (`chimera-net-check --require-inetsim`) passed before the batch
  started and before every run.
- Programs were downloaded only from vendor pages or official GitHub release pages. The
  source of each one is in `programs.csv`.
- In-house admin scripts (PowerShell, batch, shell, Python) were written for this dataset
  and are marked `authored in-house` in `source_url`. They do realistic admin work that
  looks like malware: Run keys, scheduled tasks, cron jobs, systemd user units,
  autostart entries, authorized_keys, hosts file and proxy changes, and archiving
  documents.
- Installers were started with their silent switches where the vendor provides them
  (`start_command` in `programs.csv`; `{sample}` stands for the submitted file). Portable
  tools were started with a short, realistic command line.

### Batches

| `batch` | What | Arms |
|---|---|---|
| `earlier` | First benign batch (installers, Sysinternals, Go/Rust tools, admin scripts) | Windows `A0` (baseline, unhardened) and `H3`; Linux `L` |
| `v3` | Current batch, chosen to cover malware-like benign behaviour | Windows `H3`; Linux `L` |

The `A0` runs in `earlier` show UAC prompts that `H3` does not. Use `arm == H3` if you
want Windows runs that match the current sandbox.

## Files and fields

### index.csv (one row per run)

| Field | Meaning |
|---|---|
| `os` | `windows` or `linux` |
| `sha256` | submitted file; joins to `programs.csv` |
| `name`, `version`, `category` | from `programs.csv` |
| `arm`, `run` | sandbox configuration and run number |
| `batch` | `earlier` or `v3` |
| `status` | `finished` = the run completed; anything else (`failed`, `timeout`, `stalled`) is kept on purpose |
| `telemetry_complete` | `True` when the sandbox collected the full trace for the run |
| `payload_behaviour` | `True` when the program itself did something observable (processes, files, registry, network), not just started and exited |
| `verdict`, `verdict_score` | from `classification.json`, see the warning below |
| `task_uid` | sandbox task id |
| `path` | folder holding the three JSON files |

### features.json (schema `chimera-features/1`)

| Key | Content |
|---|---|
| `sample` | sha256, file name, file type, size |
| `run` | guest OS, timeout, `complete`, `vm_stalled`, DRAKVUF error count |
| `processes` | count, max tree depth, process names, command lines, `exited_early` |
| `api_calls` | call name → count (Windows API on Windows, syscalls on Linux) |
| `api_sequence` | first calls in order |
| `files` | created / written / deleted counts and paths |
| `registry` | set / create / delete counts, keys, `autorun_touched` (Windows only; empty on Linux) |
| `network` | DNS queries, connections, remote endpoints, HTTP requests (all to INetSim) |
| `ttps` | ATT&CK-style technique tags raised by the sandbox |

### labels.json

The run record. It holds:

- `role` (always `benign` here) and `family`
- `status`, `telemetry_complete` and `payload_behaviour`
- the persistence and file-drop evidence paths, child process count and network counters
- `submitted` and `completed` timestamps (ISO 8601, UTC)

### classification.json

The verdict of the model that was running in the sandbox at the time. **For these batches
that is `chimera-stub`, a placeholder rule, not a trained classifier.** Its `label` and
`score` are not ground truth. The ground truth is `role` in `labels.json`, which is
`benign` for every run here.

### programs.csv

| Field | Meaning |
|---|---|
| `name`, `version` | program and version as downloaded |
| `category` | build or installer type and behaviour class, see below |
| `source_url` | where it was downloaded from |
| `file_name` | name the file had in the guest |
| `start_command` | how it was started (`{sample}` = the file) |
| `runs`, `run_status` | number of runs and `arm:status` for each one |

Category prefixes:

- `installer-*`: `installer-inno`, `installer-nsis`, `installer-msi-wrapper`, `installer-squirrel`, `installer-burn`
- `remote-*`, `vpn-*`, `sync-*`, `browser-*`: remote access, VPN, sync and browser installers
- `sysinternals-*`: Sysinternals tools. `-driver` / `-service` mark the ones that load a driver or install a service.
- `go-*`, `rust-*`, `c-*`, `pyinstaller-*`: build type, then what the tool does: `cli`, `network`, `server`, `crypto`, `backup`
- `admin-script-*`: `powershell`, `batch`, `shell`, `python`

## Known gaps

- **Some MSI and service behaviour is not attributed to the program.** Work done by
  `msiexec.exe` or `services.exe` on the program's behalf may run outside the program's
  process tree. Those runs can look quieter than the program really is. This is why the
  v3 batch prefers EXE installers.
- **Incomplete runs are kept.** Filter on `status` and `telemetry_complete`.
- **Network is simulated.** Programs that need a real server (sign-in, updates, peers)
  see INetSim replies, so they often stop early. Their network features show the attempt,
  not a working session.
- **One run per program in v3.** There is no run-to-run variance for these programs.
- **Verdicts are from the placeholder model.** See `classification.json` above.

## Filtering examples

```python
import pandas as pd
runs = pd.read_csv("index.csv")
good = runs[(runs.status == "finished") & (runs.telemetry_complete.astype(str) == "True")]
win_h3 = good[(good.os == "windows") & (good.arm == "H3")]
active = good[good.payload_behaviour.astype(str) == "True"]   # program did something observable
```

```python
import json, pathlib
for row in win_h3.itertuples():
    features = json.loads(pathlib.Path(row.path, "features.json").read_text())
```

To group by program type, join `index.csv` and `programs.csv` on `sha256` and use
`category`.

## What is not here

No program binaries, archives or script bodies, no credentials, and no malware. Malware
runs used for testing will go in `test-set/` when they exist.
