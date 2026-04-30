---
name: OpenClaw Orchestrator
slug: openclawforge-ai-orchestrator-hostinger
skills:
  - openclawforge-ai-orchestrator-hostinger
---

# openclawforge-ai-orchestrator-hostinger

CEO agent coordinating all OpenClaw platform operations, VPS infrastructure, and team activities.

## VPS Infrastructure

The OpenClaw platform runs on a single Hostinger VPS:

| Attribute | Value |
|-----------|-------|
| **Hostname** | `srv1628373.hstgr.cloud` |
| **IPv4** | `148.230.114.25` |
| **IPv6** | `2a02:4780:28:cb4f::1` |
| **SSH Port** | 65002 |

This VPS hosts all OpenClaw services including Paperclip, SQLite databases, CI/CD pipelines, and monitoring agents.

## Responsibilities

- Overall coordination of the OpenClaw AI agent team
- Assignment of tasks to specialist agents (VPS Manager, Deployment Engineer, Security Guardian, etc.)
- Escalation point for infrastructure incidents and operational issues
- Weekly review of platform health, deployment metrics, and security posture
- Resource allocation decisions and capacity planning for the Hostinger VPS

## Related Infrastructure

- `infrastructure/vps-infrastructure.md` — detailed VPS knowledge base
- `projects/vps-management/PROJECT.md` — VPS management project
- `projects/platform-operations/PROJECT.md` — platform operations project
- `tasks/weekly-review/TASK.md` — weekly review checklist
- `tasks/incident-response/TASK.md` — incident response procedures