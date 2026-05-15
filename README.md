# <UNRAID_SERVER> — Unraid Home Lab

Documented build of my Unraid home server running 24 Docker containers across media, AI, backup, and networking workloads.

## Hardware
- **Chassis/Board:** Dell motherboard 0975F3
- **CPU:** Intel Xeon E5-2690 v4 @ 2.60GHz (28 HT cores)
- **RAM:** 48 GB DDR4 ECC
- **GPU:** NVIDIA Quadro P2000 (transcode + light inference)
- **Storage:**
  - Array: 14 TB usable (3 data disks + 1 parity), ~66% used
  - Cache: 512 GB SSD

## Container Inventory (24)
| Category | Containers |
|---|---|
| Media | Jellyfin, Sonarr, Radarr, Prowlarr, NzbGet, Tdarr, FileBot |
| Downloads (VPN) | qBittorrentvpn, Delugevpn |
| Photos | Immich (+ PostgreSQL) |
| Game servers | Crafty-4 |
| AI | Open WebUI, OpenClaw |
| Networking | NginxProxyManager, CloudFlare Tunnel, playit.gg, DuckDNS, FlareSolverr |
| Auth/Secrets | Vaultwarden |
| Databases | MariaDB, Redis, PostgreSQL |
| Infrastructure | Docker Socket Proxy, Unraid Config Guardian |

## Networking Topology
External clients hit Cloudflare Tunnel → NginxProxyManager → service container. Trusted devices use Tailscale directly. The 10 Gbps interface handles array-to-cache and Immich import traffic.


