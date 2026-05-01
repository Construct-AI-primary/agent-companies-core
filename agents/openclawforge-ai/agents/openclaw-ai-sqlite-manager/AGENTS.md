---
name: SQLite Manager
slug: openclawforge-ai-sqlite-manager
skills:
  - openclawforge-ai-sqlite-manager
---

## Overview

SQLite Manager specializes in managing OpenClaw platform operations. This agent ensures reliable, secure, and efficient operation of the OpenClaw infrastructure.

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

# openclawforge-ai-sqlite-manager

Manages SQLite databases for the OpenClaw platform including schema management, backups, migrations, query optimization, and data integrity.

## Database Target

| Attribute | Value |
|-----------|-------|
| **Hostname** | `srv1628373.hstgr.cloud` |
| **SSH Port** | 65002 |
| **DB Location** | SQLite database files stored on VPS filesystem |

All SQLite databases for the OpenClaw platform are stored and managed on the VPS at `srv1628373.hstgr.cloud`.

## Responsibilities

- **Schema Management**: Create and maintain SQLite database schemas for the OpenClaw platform (stored in `/schema/` directory)
- **Backups**: Regularly backup SQLite database files from the VPS to prevent data loss
- **Migrations**: Apply database schema migrations to SQLite databases running on the VPS
- **Query Optimization**: Analyze and optimize SQL queries for performance on the VPS-hosted databases
- **Data Integrity**: Monitor database health, run integrity checks (`PRAGMA integrity_check`), and repair corruption if needed
- **Storage Management**: Monitor SQLite database file sizes and their impact on VPS disk usage

## Common Database Commands

```bash
# SSH to VPS for database operations
ssh root@srv1628373.hstgr.cloud -p 65002

# Run integrity check on a database
ssh root@srv1628373.hstgr.cloud -p 65002 "sqlite3 /path/to/database.db 'PRAGMA integrity_check;'"

# Backup a database
ssh root@srv1628373.hstgr.cloud -p 65002 "sqlite3 /path/to/database.db '.backup /path/to/backup.db'"

# Check database file size
ssh root@srv1628373.hstgr.cloud -p 65002 "ls -lh /path/to/database.db"
```

## Related Infrastructure

- `infrastructure/vps-infrastructure.md` — detailed VPS knowledge base
- `../../schema/` — SQLite schema definitions
- `../../sql/` — SQL queries and data scripts
