---
name: openclawforge-ai-sqlite-manager
description: >
  Use when managing SQLite databases for the OpenClaw platform, running migrations,
  creating backups, optimizing queries, maintaining data integrity, or performing CRUD
  operations on agents, companies, api_keys, issues, projects, and other core tables.
  This agent has full knowledge of the SQLite/PostgreSQL schema.
---

# SQLite Manager - OpenClaw AI Database Management

## Overview
Manages all databases used by the OpenClaw platform including schema versioning, backup and restore procedures, migration management, query optimization, and data integrity checks. Has complete awareness of the database schema to support CRUD operations for agents, agent API keys, companies, issues, projects, and other core entities.

## Schema Reference

### Core Tables

#### `agents` table
| Column | Type | Notes |
|--------|------|-------|
| `id` | UUID PK | `gen_random_uuid()` |
| `company_id` | UUID FK → companies.id | NOT NULL |
| `name` | TEXT | Agent identifier (e.g. `openclawforge-ai-vps-manager`) |
| `role` | TEXT | Default `'general'` |
| `title` | TEXT | Human-readable name |
| `status` | TEXT | Default `'idle'` — values: `idle`, `active`, `paused`, `error` |
| `reports_to` | UUID FK → agents.id | NULL for CEO agents |
| `capabilities` | TEXT | Comma-separated or description |
| `adapter_type` | TEXT | Default `'process'` |
| `adapter_config` | JSONB | Default `'{}'` |
| `context_mode` | TEXT | Default `'thin'` |
| `budget_monthly_cents` | INTEGER | Default 0 |
| `spent_monthly_cents` | INTEGER | Default 0 |
| `last_heartbeat_at` | TIMESTAMPTZ | NULL |
| `metadata` | JSONB | e.g. `{"team": "infrastructure", "specialization": "..."}` |
| `created_at` | TIMESTAMPTZ | Default NOW() |
| `updated_at` | TIMESTAMPTZ | Default NOW() |

> **⚠️ CRITICAL**: The `agents` table has `name` (identifier slug) and `title` (human-readable). Never use `slug` — that column does NOT exist in the schema.

#### `agent_api_keys` table
| Column | Type | Notes |
|--------|------|-------|
| `id` | UUID PK | |
| `agent_id` | UUID FK → agents.id | NOT NULL |
| `company_id` | UUID FK → companies.id | NOT NULL |
| `name` | TEXT | |
| `key_hash` | TEXT | NOT NULL |
| `last_used_at` | TIMESTAMPTZ | NULL |
| `revoked_at` | TIMESTAMPTZ | NULL |
| `created_at` | TIMESTAMPTZ | |

#### `companies` table
| Column | Type | Notes |
|--------|------|-------|
| `id` | UUID PK | |
| `name` | TEXT | NOT NULL (e.g. `OpenClaw AI`) |
| `description` | TEXT | |
| `status` | TEXT | Default `'active'` |
| `budget_monthly_cents` | INTEGER | Default 0 |
| `spent_monthly_cents` | INTEGER | Default 0 |
| `created_at` | TIMESTAMPTZ | |
| `updated_at` | TIMESTAMPTZ | |

#### `issues` table
| Column | Type | Notes |
|--------|------|-------|
| `id` | UUID PK | |
| `company_id` | UUID FK → companies.id | |
| `project_id` | UUID FK → projects.id | |
| `goal_id` | UUID FK → goals.id | |
| `parent_id` | UUID FK → issues.id | |
| `title` | TEXT | |
| `description` | TEXT | |
| `status` | TEXT | `backlog`, `todo`, `in_progress`, `done`, `cancelled` |
| `priority` | TEXT | `low`, `medium`, `high`, `critical` |
| `assignee_agent_id` | UUID FK → agents.id | |
| `created_by_agent_id` | UUID FK → agents.id | |
| `created_by_user_id` | TEXT | |
| `request_depth` | INTEGER | Default 0 |
| `billing_code` | TEXT | |
| `started_at` | TIMESTAMPTZ | |
| `completed_at` | TIMESTAMPTZ | |
| `cancelled_at` | TIMESTAMPTZ | |
| `created_at` | TIMESTAMPTZ | |
| `updated_at` | TIMESTAMPTZ | |

#### `projects` table
| Column | Type | Notes |
|--------|------|-------|
| `id` | UUID PK | |
| `company_id` | UUID FK → companies.id | |
| `goal_id` | UUID FK → goals.id | |
| `name` | TEXT | |
| `description` | TEXT | |
| `status` | TEXT | `backlog`, `active`, `completed`, `archived` |
| `lead_agent_id` | UUID FK → agents.id | |
| `target_date` | DATE | |
| `created_at` | TIMESTAMPTZ | |
| `updated_at` | TIMESTAMPTZ | |

#### `goals` table
| Column | Type | Notes |
|--------|------|-------|
| `id` | UUID PK | |
| `company_id` | UUID FK → companies.id | |
| `title` | TEXT | |
| `description` | TEXT | |
| `level` | TEXT | `task`, `subgoal`, `goal`, `epic` |
| `status` | TEXT | `planned`, `in_progress`, `completed` |
| `parent_id` | UUID FK → goals.id | |
| `owner_agent_id` | UUID FK → agents.id | |
| `created_at` | TIMESTAMPTZ | |
| `updated_at` | TIMESTAMPTZ | |

### Other Tables
- `activity_log` — `id`, `company_id`, `actor_type`, `actor_id`, `action`, `entity_type`, `entity_id`, `agent_id`, `details` (JSONB), `created_at`
- `approvals` — `id`, `company_id`, `type`, `requested_by_agent_id`, `status`, `payload` (JSONB), `decision_note`, `created_at`
- `cost_events` — `id`, `company_id`, `agent_id`, `issue_id`, `project_id`, `goal_id`, `billing_code`, `provider`, `model`, `input_tokens`, `output_tokens`, `cost_cents`, `occurred_at`
- `heartbeat_runs` — `id`, `company_id`, `agent_id`, `invocation_source`, `status`, `started_at`, `finished_at`, `error`, `context_snapshot` (JSONB)
- `issue_comments` — `id`, `company_id`, `issue_id`, `author_agent_id`, `author_user_id`, `body`, `created_at`, `updated_at`
- `company_skills` — `id`, `company_id`, `name`, `description`, `routing_criteria`, `capabilities` (JSONB), `is_shared`, `created_at`

## CRUD Templates

### Create a New Agent
```sql
INSERT INTO agents (
  id, company_id, name, role, title, capabilities,
  reports_to, status, metadata, created_at, updated_at
) VALUES (
  gen_random_uuid(),
  (SELECT id FROM companies WHERE name = 'OpenClaw AI'),
  'openclawforge-ai-agent-name',
  'specialist',
  'Human-Readable Name',
  'Comma-separated capabilities description',
  (SELECT id FROM agents WHERE name = 'openclawforge-ai-orchestrator-hostinger'),
  'active',
  '{"team": "infrastructure", "specialization": "..."}'::jsonb,
  NOW(), NOW()
);
```

### Register an API Key for an Agent
```sql
INSERT INTO agent_api_keys (
  id, agent_id, company_id, name, key_hash, created_at
) VALUES (
  gen_random_uuid(),
  (SELECT id FROM agents WHERE name = 'openclawforge-ai-agent-name'),
  (SELECT id FROM companies WHERE name = 'OpenClaw AI'),
  'key-name',
  '<hashed-key-value>',
  NOW()
);
```

### Look Up Company ID
```sql
SELECT id FROM companies WHERE name = 'OpenClaw AI';
```

### List All Agents for a Company
```sql
SELECT a.id, a.name, a.title, a.role, a.status,
       a.reports_to, a.capabilities, a.metadata
FROM agents a
JOIN companies c ON a.company_id = c.id
WHERE c.name = 'OpenClaw AI'
ORDER BY a.name;
```

### Update Agent Status
```sql
UPDATE agents SET status = 'active', updated_at = NOW()
WHERE name = 'openclawforge-ai-agent-name';
```

### Create an Issue
```sql
INSERT INTO issues (
  id, company_id, project_id, title, description, status, priority,
  assignee_agent_id, created_by_agent_id, created_at, updated_at
) VALUES (
  gen_random_uuid(),
  (SELECT id FROM companies WHERE name = 'OpenClaw AI'),
  NULL,
  'Issue title',
  'Issue description',
  'backlog',
  'medium',
  (SELECT id FROM agents WHERE name = 'openclawforge-ai-assignee'),
  (SELECT id FROM agents WHERE name = 'openclawforge-ai-orchestrator-hostinger'),
  NOW(), NOW()
);
```

## When to Use
- When running database migrations or schema changes
- When creating or restoring SQLite database backups
- When optimizing slow queries or database performance
- When checking or repairing data integrity
- When troubleshooting database errors or corruption
- When creating new agents that need database entries
- When looking up agent IDs, company IDs, or foreign key relationships
- When registering API keys for new or existing agents
- When querying agent status, assignments, or metadata