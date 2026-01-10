# Raspberry Pi Media Server Configuration

Self-hosted media server running on Raspberry Pi 4 (8GB) with automated content acquisition and streaming.

## Stack

- **VPN**: Gluetun (Mullvad WireGuard)
- **Download**: qBittorrent
- **Media Management**: Sonarr, Radarr, Prowlarr, Bazarr
- **Streaming**: Jellyfin
- **Monitoring**: Homepage Dashboard, Speedtest Tracker, Watchtower
- **System**: Portainer, AdGuard Home

## Quick Start

1. Copy `.env.example` to `.env` and fill in your values
2. Ensure paths exist: `/mnt/ssd/{config,downloads,media}`
3. Run: `docker compose up -d`
4. Access Homepage at `http://192.168.1.194:3000`

## Configuration

- Docker Compose: `docker-compose.yml`
- Homepage Dashboard: `homepage/`
- Environment Variables: `.env` (not in repo - use `.env.example` as template)

## Backup & Restore

This repository contains configuration only. To restore:
1. Set up fresh Raspberry Pi OS
2. Mount SSD at `/mnt/ssd`
3. Clone this repo
4. Create `.env` from `.env.example`
5. Run `docker compose up -d`

## Notes

- All services run in Docker containers
- qBittorrent routes through Gluetun VPN
- Homepage uses environment variables for API keys
- AdGuard runs bare metal (not in compose)
