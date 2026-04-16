# Netdata for Raspberry Pi

Minimal Netdata dashboard for Raspberry Pi, running in Docker.

## Features

- Real-time monitoring: CPU usage, CPU temperature, memory, disk, network, I/O
- Time window selector: **5m live** / 1h / 6h / 24h historical view
- Compact dark-themed dashboard optimized for Raspberry Pi

## Usage

Build image and start container:

```bash
./netdata.sh
```

Then open `http://[your-Pi-IP]:19999/rpi.html` in a browser.

### Options

| Flag | Description |
|------|-------------|
| `-p` | Pull latest Netdata image before build |
| `-h` | Show help |

## Requirements

- Docker
- Raspberry Pi (tested on Pi 4)

## Based on

Original project by **[Signal Flag Z](https://signal-flag-z.blogspot.com/)**:  
[github.com/SignalFlagZ/Dockerfiles](https://github.com/SignalFlagZ/Dockerfiles)

### Changes from original

- Rewrote `rpi.html` dashboard using Chart.js 4 for compatibility with Netdata v2 API
- Added time window selector (5m live / 1h / 6h / 24h)
- Fixed data update loop to handle Netdata v2 descending sort order
- Fixed disk space unit (GB, not MB) for Netdata v2
