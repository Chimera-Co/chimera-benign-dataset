# Benign batch v3 (generated 2026-10-22T22:38:42+00:00)

Windows arm H3, Linux arm L; 180 s per run; 1 run per program; INetSim network.

| OS | Done / scheduled | Finished | Telemetry complete | Payload behaviour | Persistence | Network intent | Other statuses |
|---|---|---|---|---|---|---|---|
| windows | 5 / 75 | 5 | 5 | 2 | 0 | 1 | – |
| linux | 13 / 44 | 13 | 13 | 10 | 5 | 2 | – |

## Runs by category

| OS | Category | Runs | Finished | Payload behaviour |
|---|---|---|---|---|
| windows | admin-script-batch | 1 | 1 | 0 |
| windows | admin-script-powershell | 1 | 1 | 1 |
| windows | sync-installer | 1 | 1 | 1 |
| windows | sysinternals-cli | 2 | 2 | 0 |
| linux | admin-script-shell | 3 | 3 | 3 |
| linux | go-cli | 2 | 2 | 1 |
| linux | go-crypto | 2 | 2 | 2 |
| linux | go-network | 2 | 2 | 2 |
| linux | go-server | 1 | 1 | 0 |
| linux | rust-cli | 3 | 3 | 2 |

## Runs

| OS | Program | Category | Status | Telemetry complete | Payload | Persistence | Children | Network |
|---|---|---|---|---|---|---|---|---|
| linux | age 1.3.2 | go-crypto | finished | yes | yes | no | 2 | no |
| linux | autostart-agent 1.0 | admin-script-shell | finished | yes | yes | yes | 13 | no |
| linux | bashrc-setup 1.0 | admin-script-shell | finished | yes | yes | yes | 7 | no |
| linux | cloudflared 2026.10.3 | go-network | finished | yes | yes | no | 1 | yes |
| linux | delta 0.20.1 | rust-cli | finished | yes | no | no | 4 | no |
| linux | duf 0.9.1 | go-cli | finished | yes | no | no | 1 | no |
| linux | frpc 0.71.1 | go-network | finished | yes | yes | no | 1 | no |
| linux | glow 3.0.0 | go-cli | finished | yes | yes | no | 1 | no |
| linux | mkcert 1.4.4 | go-crypto | finished | yes | yes | no | 3 | no |
| linux | navi 2.24.0 | rust-cli | finished | yes | yes | yes | 2 | no |
| linux | ssh-key-sync 1.0 | admin-script-shell | finished | yes | yes | yes | 8 | yes |
| linux | traefik 3.7.16 | go-server | finished | yes | no | no | 1 | no |
| linux | zoxide 0.10.0 | rust-cli | finished | yes | yes | yes | 3 | no |
| windows | accesschk latest | sysinternals-cli | finished | yes | no | no | 1 | no |
| windows | backup-documents 1.0 | admin-script-powershell | finished | yes | yes | no | 3 | no |
| windows | dropbox 274.4.4905 | sync-installer | finished | yes | yes | no | 5 | yes |
| windows | listdlls latest | sysinternals-cli | finished | yes | no | no | 1 | no |
| windows | log-collector 1.0 | admin-script-batch | finished | yes | no | no | 6 | no |
