# Benign batch v3 (generated 2026-10-23T02:49:27+00:00)

Windows arm H3, Linux arm L; 180 s per run; 1 run per program; INetSim network.

| OS | Done / scheduled | Finished | Telemetry complete | Payload behaviour | Persistence | Network intent | Other statuses |
|---|---|---|---|---|---|---|---|
| windows | 28 / 75 | 28 | 28 | 17 | 3 | 8 | – |
| linux | 40 / 44 | 40 | 39 | 25 | 6 | 7 | – |

## Runs by category

| OS | Category | Runs | Finished | Payload behaviour |
|---|---|---|---|---|
| windows | admin-script-batch | 1 | 1 | 0 |
| windows | admin-script-powershell | 3 | 3 | 3 |
| windows | browser-installer | 1 | 1 | 1 |
| windows | go-backup | 2 | 2 | 0 |
| windows | installer-inno | 3 | 3 | 2 |
| windows | installer-msi-wrapper | 1 | 1 | 1 |
| windows | installer-nsis | 2 | 2 | 2 |
| windows | installer-stub-downloader | 1 | 1 | 1 |
| windows | network-cli | 1 | 1 | 1 |
| windows | network-tool-installer | 1 | 1 | 1 |
| windows | remote-access-installer | 2 | 2 | 2 |
| windows | rust-cli | 2 | 2 | 0 |
| windows | sync-installer | 1 | 1 | 1 |
| windows | sysinternals-cli | 6 | 6 | 1 |
| windows | vpn-installer | 1 | 1 | 1 |
| linux | admin-script-python | 1 | 1 | 1 |
| linux | admin-script-shell | 7 | 7 | 7 |
| linux | c-cli | 1 | 1 | 0 |
| linux | go-cli | 9 | 9 | 6 |
| linux | go-crypto | 3 | 3 | 3 |
| linux | go-network | 5 | 5 | 5 |
| linux | go-server | 3 | 3 | 1 |
| linux | rust-cli | 9 | 9 | 2 |
| linux | rust-network | 1 | 1 | 0 |
| linux | rust-server | 1 | 1 | 0 |

## Runs

| OS | Program | Category | Status | Telemetry complete | Payload | Persistence | Children | Network |
|---|---|---|---|---|---|---|---|---|
| linux | age 1.3.2 | go-crypto | finished | yes | yes | no | 2 | no |
| linux | autostart-agent 1.0 | admin-script-shell | finished | yes | yes | yes | 13 | no |
| linux | bashrc-setup 1.0 | admin-script-shell | finished | yes | yes | yes | 7 | no |
| linux | bat 0.26.1 | rust-cli | finished | yes | no | no | 1 | no |
| linux | cloudflared 2026.10.3 | go-network | finished | yes | yes | no | 1 | yes |
| linux | croc 11.5.5 | go-network | finished | yes | yes | no | 1 | yes |
| linux | cron-health 1.0 | admin-script-shell | finished | yes | yes | yes | 14 | no |
| linux | delta 0.20.1 | rust-cli | finished | yes | no | no | 4 | no |
| linux | disk-usage-report 1.0 | admin-script-python | finished | yes | yes | no | 2 | no |
| linux | dive 0.13.1 | go-cli | finished | yes | no | no | 2 | no |
| linux | duf 0.9.1 | go-cli | finished | yes | no | no | 1 | no |
| linux | dust 1.2.6 | rust-cli | finished | yes | no | no | 1 | no |
| linux | eza 0.23.5 | rust-cli | finished | yes | no | no | 2 | no |
| linux | fd 10.5.0 | rust-cli | finished | yes | no | no | 1 | no |
| linux | frpc 0.71.1 | go-network | finished | yes | yes | no | 1 | no |
| linux | frps 0.71.1 | go-network | finished | yes | yes | no | 1 | no |
| linux | gdu 5.38.0 | go-cli | finished | yes | no | no | 1 | no |
| linux | gh 2.103.0 | go-network | finished | yes | yes | no | 3 | no |
| linux | glow 3.0.0 | go-cli | finished | yes | yes | no | 1 | no |
| linux | gron 0.7.1 | go-cli | finished | yes | yes | no | 3 | yes |
| linux | hugo 0.168.0 | go-cli | finished | yes | yes | no | 2 | no |
| linux | hyperfine 2.0.0 | rust-cli | finished | yes | no | no | 246 | no |
| linux | jq 1.8.2 | c-cli | finished | yes | no | no | 3 | no |
| linux | k9s 0.51.0 | go-cli | finished | yes | yes | no | 2 | no |
| linux | log-rotate-archive 1.0 | admin-script-shell | finished | yes | yes | no | 13 | yes |
| linux | micro 2.0.15 | go-cli | finished | yes | yes | no | 2 | no |
| linux | miniserve 0.35.0 | rust-server | finished | yes | no | no | 1 | no |
| linux | mkcert 1.4.4 | go-crypto | finished | yes | yes | no | 3 | no |
| linux | nats-server 2.15.1 | go-server | finished | yes | no | no | 1 | no |
| linux | navi 2.24.0 | rust-cli | finished | yes | yes | yes | 2 | no |
| linux | net-recon 1.0 | admin-script-shell | finished | yes | yes | no | 14 | yes |
| linux | proc-audit 1.0 | admin-script-shell | finished | no | yes | no | 127 | no |
| linux | prometheus 3.15.1 | go-server | finished | yes | yes | no | 1 | no |
| linux | sops 3.13.3 | go-crypto | finished | yes | yes | no | 2 | yes |
| linux | ssh-key-sync 1.0 | admin-script-shell | finished | yes | yes | yes | 8 | yes |
| linux | traefik 3.7.16 | go-server | finished | yes | no | no | 1 | no |
| linux | websocat 1.14.1 | rust-network | finished | yes | no | no | 1 | no |
| linux | yazi 26.9.1 | rust-cli | finished | yes | no | no | 2 | no |
| linux | yq 4.54.1 | go-cli | finished | yes | yes | no | 1 | no |
| linux | zoxide 0.10.0 | rust-cli | finished | yes | yes | yes | 3 | no |
| windows | 7zip 23.01 | installer-nsis | finished | yes | yes | no | 0 | no |
| windows | accesschk latest | sysinternals-cli | finished | yes | no | no | 1 | no |
| windows | backup-documents 1.0 | admin-script-powershell | finished | yes | yes | no | 3 | no |
| windows | curl 8.23.0 | network-cli | finished | yes | yes | no | 2 | yes |
| windows | dropbox 274.4.4905 | sync-installer | finished | yes | yes | no | 5 | yes |
| windows | dust 1.2.6 | rust-cli | finished | yes | no | no | 1 | no |
| windows | firefox 158.0.1 | browser-installer | finished | yes | yes | no | 11 | yes |
| windows | hyperfine 2.0.0 | rust-cli | finished | yes | no | no | 2 | no |
| windows | keepass 2.61.1 | installer-inno | finished | yes | yes | yes | 14 | no |
| windows | kopia 0.23.1 | go-backup | finished | yes | no | no | 1 | no |
| windows | listdlls latest | sysinternals-cli | finished | yes | no | no | 1 | no |
| windows | localsend 1.18.2 | installer-inno | finished | yes | no | no | 1 | no |
| windows | log-collector 1.0 | admin-script-batch | finished | yes | no | no | 6 | no |
| windows | nmap 7.992 | network-tool-installer | finished | yes | yes | no | 0 | no |
| windows | obs-studio 32.2.2 | installer-nsis | finished | yes | yes | no | 4 | no |
| windows | psinfo latest | sysinternals-cli | finished | yes | no | no | 1 | no |
| windows | pslist latest | sysinternals-cli | finished | yes | no | no | 1 | no |
| windows | psservice latest | sysinternals-cli | finished | yes | no | no | 1 | no |
| windows | restic 0.19.1 | go-backup | finished | yes | no | no | 1 | no |
| windows | rustdesk 1.5.0 | remote-access-installer | finished | yes | yes | no | 69 | no |
| windows | security-baseline 1.0 | admin-script-powershell | finished | yes | yes | no | 5 | yes |
| windows | sigcheck latest | sysinternals-cli | finished | yes | yes | no | 1 | yes |
| windows | software-installer 1.0 | admin-script-powershell | finished | yes | yes | yes | 1 | yes |
| windows | spotify latest | installer-stub-downloader | finished | yes | yes | no | 0 | yes |
| windows | tailscale 1.104.2 | vpn-installer | finished | yes | yes | yes | 2 | yes |
| windows | teamviewer 15 | remote-access-installer | finished | yes | yes | no | 5 | no |
| windows | telegram 7.3.3 | installer-inno | finished | yes | yes | no | 1 | no |
| windows | zoom 6.6.11 | installer-msi-wrapper | finished | yes | yes | no | 1 | no |
