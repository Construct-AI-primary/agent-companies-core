---
name: VPS Infrastructure Knowledge
description: Detailed knowledge base for the OpenClaw Hostinger VPS infrastructure
tags:
  - vps
  - hostinger
  - infrastructure
  - srv1628373
---

# VPS Infrastructure Knowledge — `srv1628373.hstgr.cloud`

## Primary VPS Host

| Attribute | Value |
|-----------|-------|
| **Hostname** | `srv1628373.hstgr.cloud` |
| **Provider** | Hostinger VPS |
| **IPv4 Address** | `148.230.114.25` |
| **IPv6 Address** | `2a02:4780:28:cb4f::1` |
| **Reverse DNS** | `srv1628373.hstgr.cloud` |
| **SSH Port** | 65002 |
| **SSH User** | root |
| **OS** | Ubuntu 24.04 LTS |
| **Location** | France — Paris |
| **Plan** | KVM 2 |
| **CPU** | 2 cores |
| **RAM** | 8 GB |
| **Disk** | 100 GB SSD |
| **Expiration** | 2027-04-30 (auto-renewal on) |
| **Uptime** | 7 hours (as of 2026-04-30) |

## Hostinger API

The Hostinger API is used for VPS CRUD operations. API tokens should be stored securely.

```bash
# API base URL
HOSTINGER_API_BASE="https://api.hostinger.com/v1"
```

### Key API Use Cases

| Operation | Endpoint | Agent |
|-----------|----------|-------|
| List VPS | `GET /vps` | VPS Manager |
| Get VPS Metrics | `GET /vps/{id}/metrics` | Monitoring Specialist, VPS Manager |
| Create Snapshot | `POST /vps/{id}/snapshots` | VPS Manager |
| Reboot VPS | `POST /vps/{id}/reboot` | Systems Administrator |
| Get Firewall Rules | `GET /vps/{id}/firewall` | Security Guardian |
| Update Firewall Rules | `PUT /vps/{id}/firewall` | Security Guardian |

## Services & Applications

The following services run on this VPS to support the OpenClaw platform:

1. **Paperclip Application** — The primary Paperclip SaaS application (running at paperclip.agentcompanies.com or similar)
2. **SQLite Databases** — Platform databases stored on this VPS
3. **CI/CD Agents** — Deployment pipelines execute on this VPS
4. **Monitoring & Alerting** — System health monitoring runs locally

## SSH Access

To connect to the VPS:
```bash
ssh root@srv1628373.hstgr.cloud -p 65002
# Or using IPv4 directly:
ssh root@148.230.114.25 -p 65002
# Or using IPv6:
ssh root@2a02:4780:28:cb4f::1 -p 65002
```

## Network Configuration

- **IPv4**: `148.230.114.25` — primary public IPv4 address
- **IPv6**: `2a02:4780:28:cb4f::1` — IPv6 connectivity
- **SSH Port**: 65002 (non-standard, reduces automated attack surface)
- **Reverse DNS**: `srv1628373.hstgr.cloud` resolves to both addresses

## Security Configuration

- SSH on non-standard port **65002** (reduces automated attacks)
- UFW/iptables firewall rules restrict inbound traffic
- SSL/TLS certificates managed for public-facing services
- Regular security patches via apt

## Storage & Resource Management

- Monitor disk usage regularly (SQLite databases can grow)
- Manage snapshots via Hostinger panel or API
- Resource scaling (CPU/RAM) handled through Hostinger control panel

## Backup & Recovery

- Regular SQLite database backups
- VPS-level snapshots via Hostinger
- Disaster recovery procedures documented in incident response tasks

## Related Agents

| Agent | Role | CRUD Mechanism |
|-------|------|----------------|
| VPS Manager | Provisioning, scaling, snapshots, resource allocation | Hostinger API |
| Systems Administrator | OS updates, packages, disk, users | SSH |
| Deployment Engineer | Application deployments, CI/CD | SSH + Git |
| Security Guardian | Firewalls, SSH, SSL, patches, intrusion detection | SSH + Hostinger API |
| Monitoring Specialist | Health metrics, uptime, logs, alerting | SSH + Hostinger API |
| Config Manager | Environment variables, .env, secrets | SSH |
| SQLite Manager | Database schema, backups, migrations | SSH + sqlite3 |
| Agent Creator | Agent lifecycle management | SQLite DB (via SQLite Manager) |
| Model Assigner | AI model assignments | SQLite DB (via SQLite Manager) |
| Orchestrator | Overall coordination | Coordinates all above |