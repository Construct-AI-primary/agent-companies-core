---
name: Incident Response
description: Incident response procedure for OpenClaw platform issues and outages
schedule: on-demand
lead_agent: openclawforge-ai-orchestrator-hostinger
tags:
  - incident
  - response
  - operations
---

# Incident Response

Standard operating procedure for responding to platform incidents on the Hostinger VPS (`srv1628373.hstgr.cloud`, IPv4: `148.230.114.25`, SSH port 65002).

## Response Steps
1. **Detection**: Alert triggered by monitoring specialist or external report for `srv1628373.hstgr.cloud`
2. **Diagnosis**: Identify affected services and root cause on the VPS (SSH: `ssh root@srv1628373.hstgr.cloud -p 65002`)
3. **Containment**: Isolate affected systems if needed (firewall rules, service shutdown)
4. **Resolution**: Apply fix or workaround on the VPS
5. **Recovery**: Restore normal operations and verify service health
6. **Post-mortem**: Document incident, cause, and prevention

## Related Agents
- openclawforge-ai-orchestrator-hostinger
- openclawforge-ai-monitoring-specialist
- openclawforge-ai-systems-administrator
- openclawforge-ai-security-guardian

## Related Documents
- `infrastructure/vps-infrastructure.md` — detailed VPS knowledge base
- `tasks/weekly-review/TASK.md` — weekly health review checklist
