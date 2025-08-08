# Home Lab: AdGuard Home – DNS Filtering in Docker

## Project goals:
- Deploy AdGuard Home in Docker container
- Provide network-wide DNS-based ad blocking
- Configure persistent storage for AdGuard Home data
- Learn Docker container management (`docker run` & `docker-compose`)
- Integrate AdGuard Home with existing home lab infrastructure

## Technologies:
- **Proxmox VE** – Hypervisor
- **Ubuntu Server LTS** – VM for Docker
- **Docker & Docker Compose** – container management
- **AdGuard Home** – DNS filtering service
- **Local Network Clients** – using AdGuard as DNS server

## Main functions and configuration
- Containerized AdGuard Home using official Docker image
- Persistent volumes for:
  - `/opt/adguardhome/conf` – configuration
  - `/opt/adguardhome/work` – runtime data
- Port mapping:
  - `53/udp` – DNS service
  - `80/tcp` – web interface
  - `3000/tcp` – initial setup wizard
- Configured to listen on all interfaces (`0.0.0.0`)
- Accessible from LAN clients via VM IP (`192.168.1.xxx`)

## Repository structure
```
.
├── README.md
├── docs/
│   └── screenshots/
├── config/
    └── white-lists/
```

## To future implementation
- Add DNS blocklists (ads, tracking, malware)
- Enable DoH (DNS-over-HTTPS) for clients
- Configure AdGuard Home statistics and reporting
- Integrate with NGFW (Sophos XG) as upstream DNS
- Backup & restore scripts for configuration
- Example client configuration guides (Windows, macOS, Android, iOS)
