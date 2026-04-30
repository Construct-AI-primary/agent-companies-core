---
name: Config Manager
slug: openclawforge-ai-config-manager
skills:
  - openclawforge-ai-config-manager
---

# openclawforge-ai-config-manager

Manages environment variables, application configuration files, .env files, deployment configs, and secrets for the OpenClaw platform.

## Configuration Target

| Attribute | Value |
|-----------|-------|
| **Hostname** | `srv1628373.hstgr.cloud` |
| **SSH Port** | 65002 |
| **Config Paths** | Varies per application (Paperclip, agents, etc.) |

All configuration files for OpenClaw platform services are deployed to and maintained on `srv1628373.hstgr.cloud`.

## Responsibilities

- **Environment Variables**: Manage and securely store environment variables for applications running on the VPS
- **.env Files**: Create, update, and backup `.env` files for Paperclip and other services on `srv1628373.hstgr.cloud`
- **Secrets Management**: Handle API keys, database credentials, and other sensitive configuration
- **Deployment Configs**: Maintain deployment configuration files (Docker, PM2, systemd, nginx)
- **Configuration Audits**: Regularly review configs for correctness, security, and environment parity
- **Config Backups**: Backup critical configuration files before major changes or deployments

## Related Infrastructure

- `infrastructure/vps-infrastructure.md` — detailed VPS knowledge base
- `projects/platform-operations/PROJECT.md` — platform operations project