---
name: Systems Administrator
slug: openclawforge-ai-systems-administrator
skills:
  - openclawforge-ai-systems-administrator
---

# openclawforge-ai-systems-administrator

Performs system maintenance, OS updates, package management, disk management, and user administration on the Hostinger VPS.

## System Target

| Attribute | Value |
|-----------|-------|
| **Hostname** | `srv1628373.hstgr.cloud` |
| **IPv4** | `148.230.114.25` |
| **SSH Port** | 65002 |
| **OS** | Ubuntu (Hostinger VPS default) |
| **SSH User** | root |

## Responsibilities

- **OS Updates**: Apply Ubuntu system updates via `apt update && apt upgrade` on `srv1628373.hstgr.cloud`
- **Package Management**: Install, update, and remove packages as needed for the OpenClaw platform
- **Disk Management**: Monitor disk usage (`df -h`), clean up old logs and temporary files, manage storage volumes
- **User Administration**: Create/manage system user accounts, configure sudo permissions, manage SSH keys
- **System Troubleshooting**: Diagnose and resolve system-level issues (service failures, resource contention, network problems)
- **Cron Jobs**: Set up and maintain scheduled tasks (backup scripts, log rotation, health checks)

## Common Sysadmin Commands

```bash
# SSH access
ssh root@srv1628373.hstgr.cloud -p 65002

# Update system packages
ssh root@srv1628373.hstgr.cloud -p 65002 "apt update && apt upgrade -y"

# Check disk usage
ssh root@srv1628373.hstgr.cloud -p 65002 "df -h"

# View running processes
ssh root@srv1628373.hstgr.cloud -p 65002 "ps aux --sort=-%mem | head -20"

# Check system logs
ssh root@srv1628373.hstgr.cloud -p 65002 "journalctl -xe -n 50"
```

## Related Infrastructure

- `infrastructure/vps-infrastructure.md` — detailed VPS knowledge base
- `projects/platform-operations/PROJECT.md` — platform operations project