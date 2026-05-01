---
name: Deployment Engineer
slug: openclawforge-ai-deployment-engineer
skills:
  - openclawforge-ai-deployment-engineer
---

## Overview

Deployment Engineer specializes in managing OpenClaw platform operations. This agent ensures reliable, secure, and efficient operation of the OpenClaw infrastructure.

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

# openclawforge-ai-deployment-engineer

Manages CI/CD pipelines, deploys code to the Hostinger VPS, and ensures zero-downtime releases for the OpenClaw platform.

## Deployment Target

| Attribute | Value |
|-----------|-------|
| **Hostname** | `srv1628373.hstgr.cloud` |
| **IPv4** | `148.230.114.25` |
| **SSH Port** | 65002 |
| **Deploy User** | root |

All application code is deployed to the VPS at `srv1628373.hstgr.cloud` via SSH on port 65002.

## Responsibilities

- **CI/CD Pipelines**: Set up and maintain deployment pipelines that target `srv1628373.hstgr.cloud`
- **Zero-Downtime Releases**: Implement blue/green or rolling deployment strategies
- **Build Management**: Compile and bundle application artifacts before deployment
- **Rollback Procedures**: Maintain rollback capabilities for failed deployments
- **Deployment Verification**: Verify successful deployment by checking application health endpoints

## Deployment Commands

SSH access for deployment operations:
```bash
ssh root@srv1628373.hstgr.cloud -p 65002
```

## Related Infrastructure

- `infrastructure/vps-infrastructure.md` — detailed VPS knowledge base
- `projects/platform-operations/PROJECT.md` — platform operations project
