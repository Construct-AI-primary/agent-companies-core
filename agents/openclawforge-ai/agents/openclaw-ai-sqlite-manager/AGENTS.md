---
name: SQLite Manager
slug: openclawforge-ai-sqlite-manager
skills:
  - openclawforge-ai-sqlite-manager
---

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