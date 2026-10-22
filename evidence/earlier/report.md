# M5 results: Windows A0 vs H3, Linux, benign

Runs: 42 of 42 scheduled; incomplete telemetry (excluded): 0; executed hash differs from register: 0; egress drops: 0.

## Paired outcome (test samples, payload behaviour observed)

| | H3 observed | H3 not observed |
|---|---|---|
| **A0 observed** | 0 | 0 |
| **A0 not observed** | 0 | 0 |

Paired samples: 0; excluded (no complete run in an arm): 0.
Exact McNemar test on the discordant pairs (0 A0-only vs 0 H3-only): p = 1.000. Exploratory: the sample is small.

## Per sample

| SHA-256 | Role | Family | A0 observed | H3 observed | A0 children | H3 children | A0 network | H3 network | Complete runs (A0/H3) |
|---|---|---|---|---|---|---|---|---|---|

## Benign samples (false-positive check)

| OS | Name | SHA-256 | Runs | Complete | Payload observed | Persistence | Drops | Network | Verdicts |
|---|---|---|---|---|---|---|---|---|---|
| linux | Backup setup (crontab, systemd timer) | `880d7d792db0` | 1 | 1 | yes | 1 | 1 | 0 | – |
| linux | BusyBox static | `6e123e7f3202` | 1 | 1 | yes | 0 | 1 | 1 | – |
| linux | Caddy (serves home over HTTP) | `678ade3bfc08` | 1 | 1 | yes | 0 | 1 | 0 | – |
| linux | Monitoring agent (HTTP POST beacon) | `1e05da69cc62` | 1 | 1 | yes | 0 | 1 | 1 | – |
| linux | Prometheus node_exporter (listener) | `1108f7453ecf` | 1 | 1 | no | 0 | 0 | 0 | – |
| linux | Syncthing (sync, Go) | `d72663e4f9ef` | 1 | 1 | yes | 0 | 1 | 1 | – |
| linux | System info report (tar archive) | `cc416007a051` | 1 | 1 | yes | 0 | 1 | 0 | – |
| linux | Tool installer (download, chmod, PATH) | `3db278379f74` | 1 | 1 | yes | 0 | 1 | 1 | – |
| linux | Workstation provisioning (authorized_keys, autostart) | `02bad5a153ad` | 1 | 1 | yes | 1 | 1 | 1 | – |
| linux | rclone (sync, Go) | `ed7ab1f17876` | 1 | 1 | yes | 0 | 1 | 1 | – |
| linux | restic (encrypted backup, Go) | `20d4142678d0` | 1 | 1 | yes | 0 | 1 | 0 | – |
| linux | ripgrep (searches for secrets) | `e62198eb19b1` | 1 | 1 | no | 0 | 0 | 0 | – |
| windows | AnyDesk portable (remote access) | `2a85e3bc09a2` | 2 | 2 | yes | 0 | 0 | 2 | – |
| windows | Everything installer (NSIS, service) | `874e87dc9de6` | 2 | 2 | yes | 2 | 2 | 0 | – |
| windows | Greenshot installer (Inno) | `5d6ec298fb30` | 2 | 2 | yes | 2 | 2 | 2 | – |
| windows | IT inventory script (scheduled task, HTTP POST) | `a0c274b22ca6` | 2 | 2 | yes | 0 | 2 | 2 | – |
| windows | KeePassXC MSI | `feee096c1d5d` | 2 | 2 | no | 0 | 0 | 0 | – |
| windows | Logon script (Run key, recon) | `a83ed1fe65eb` | 2 | 2 | yes | 2 | 2 | 2 | – |
| windows | Syncthing (sync, Go) | `e33d934db704` | 2 | 2 | yes | 0 | 0 | 2 | – |
| windows | Sysinternals Autoruns CLI | `093d1c6b91d2` | 2 | 2 | no | 0 | 0 | 0 | – |
| windows | Sysinternals BGInfo | `ee2c4850e622` | 2 | 2 | no | 0 | 0 | 0 | – |
| windows | Sysinternals ProcDump (full dump) | `22c2a2b09ade` | 2 | 2 | no | 0 | 0 | 0 | – |
| windows | Sysinternals PsExec (service as SYSTEM) | `edfae1a69522` | 2 | 2 | yes | 0 | 2 | 2 | – |
| windows | TightVNC server MSI (remote access) | `aa256612c5b8` | 2 | 2 | no | 0 | 0 | 0 | – |
| windows | VC++ redistributable | `cc0ff0eb1dc3` | 2 | 2 | yes | 0 | 2 | 0 | – |
| windows | WinRAR installer | `0c9a2a3d70d9` | 2 | 2 | yes | 0 | 2 | 0 | – |
| windows | rclone (sync, Go) | `41eab3e118d2` | 2 | 2 | yes | 0 | 0 | 1 | – |
