---
name: Renderservicemanager
slug: saasforge-ai-renderservicemanager
reportsTo: saasforge-ai-onboardmaster
role: general
description: >
  Use when creating new Render services, managing Render infrastructure, configuring auto-scaling, or handling Render-specific deployments. This skill manages Render platform operations.

skills:
  - saasforge-ai-renderservicemanager
---

## Overview

Render Service Manager specializes in creating, configuring, and managing Render services for the white-label multi-client platform, automating service provisioning and lifecycle management.

## When To Use

- When creating new client Render services
- When provisioning databases per client
- When configuring render.yaml files
- When managing service scaling
- When setting up domains and SSL
- **Don't use when:** Deployment orchestration needed (use Deployment-Orchestrator), or GitHub configuration needed (use GitHub-Branch-Manager)

## Core Procedures

### New Client Service Provisioning
1. **Service Plan** - Determine required plan based on client needs
2. **render.yaml Creation** - Create service configuration
3. **Service Creation** - Create service via Render API
4. **Database Provisioning** - Create PostgreSQL database
5. **Environment Variables** - Set all required env vars
6. **Domain Configuration** - Configure custom domain
7. **SSL Setup** - Enable automatic SSL
8. **Health Check** - Verify service is healthy

### render.yaml Configuration
```yaml
# render.yaml
services:
  - type: web
    name: companya-app
    env: node
    region: oregon
    branch: main
    repo: https://github.com/yourorg/companya-system
    buildCommand: npm ci && npm run build
    startCommand: npm start
    healthCheckPath: /health
    envVars:
      - key: NODE_ENV
        value: production
      - key: DATABASE_URL
        fromDatabase:
          name: companya-db
          color: blue

databases:
  - name: companya-db
    databaseName: companya_db
    plan: starter
    color: blue
```

### Auto-Scaling Configuration
```yaml
auto_scaling:
  min_instances: 1
  max_instances: 10
  target_cpu_percent: 70
  target_memory_percent: 80
  scale_up_cooldown: 300
  scale_down_cooldown: 600
```

### Domain & SSL Management
1. **Domain Verification** - Verify DNS ownership
2. **SSL Certificate** - Automatic via Let's Encrypt
3. **WWW Redirect** - Configure www to non-www redirect
4. **Custom Domain** - Point client domain to service
