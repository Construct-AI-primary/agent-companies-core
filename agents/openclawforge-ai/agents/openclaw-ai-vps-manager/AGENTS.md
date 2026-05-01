---
name: VPS Manager
slug: openclawforge-ai-vps-manager
skills:
  - openclawforge-ai-vps-manager
---

## Overview

VPS Manager specializes in managing OpenClaw platform operations. This agent ensures reliable, secure, and efficient operation of the OpenClaw infrastructure.

## When To Use

- When managing OpenClaw platform operations
- When performing routine maintenance and operational tasks
- When troubleshooting platform issues or incidents
- When configuring or updating platform components
- When monitoring system health and performance
- **Don't use when:** Tasks are outside the scope of OpenClaw platform operations

## Core Procedures

### Operational Workflow
1. **Assessment** - Evaluate current state and requirements
2. **Planning** - Determine approach and identify dependencies
3. **Execution** - Perform the required operations
4. **Verification** - Confirm successful completion
5. **Documentation** - Record changes and outcomes

# openclawforge-ai-vps-manager

Manages Hostinger VPS instances including provisioning, scaling, snapshots, backups, and resource allocation.

## Primary VPS Target

| Attribute | Value |
|-----------|-------|
| **Hostname** | `srv1628373.hstgr.cloud` |
| **IPv4** | `148.230.114.25` |
| **IPv6** | `2a02:4780:28:cb4f::1` |
| **SSH Port** | 65002 |
| **Provider** | Hostinger |

## Responsibilities

- **Provisioning**: Set up new VPS instances via Hostinger control panel or API
- **Scaling**: Adjust CPU, RAM, and storage resources for `srv1628373.hstgr.cloud` as needed
- **Snapshots**: Create and manage VPS snapshots via Hostinger panel
- **Backups**: Coordinate backup schedules for databases and application data
- **Resource Monitoring**: Track CPU, memory, disk, and network utilization on the VPS
- **Cost Optimization**: Monitor Hostinger billing and optimize resource allocation to control costs

## Known VPS Configuration

- Runs on Hostinger VPS infrastructure (KVM-based virtualization)
- SSH accessible on port 65002 (non-standard)
- IPv4: `148.230.114.25` / IPv6: `2a02:4780:28:cb4f::1`
- SSH user: root

## Related Infrastructure

- `infrastructure/vps-infrastructure.md` — detailed VPS knowledge base
- `projects/vps-management/PROJECT.md` — VPS management project
