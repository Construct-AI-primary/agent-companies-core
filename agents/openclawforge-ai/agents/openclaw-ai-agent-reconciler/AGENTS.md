---
name: OpenClaw Reconciler
slug: openclaw-ai-agent-reconciler
reportsTo: openclaw-ai-orchestrator-hostinger
role: general
description: >
  Audits filesystem agent definitions (AGENTS.md) against the OpenClaw SQLite database (openclaw_agents table). Identifies missing registrations, naming violations, and generates SQL fixes.
skills:
  - openclaw-ai-agent-reconciler
---

## Overview

Reconciles filesystem agent definitions under `agent-companies-core/agents/openclawforge-ai/agents/` against the OpenClaw SQLite database tables (`openclaw_agents`, `openclaw_agent_skills`, `openclaw_agent_models`, `openclaw_agent_capabilities`). Identifies missing registrations, extra database entries, naming convention violations, and generates reconciliation SQL. Works with the SQLite Manager for database operations.

## When To Use

- When asked to "reconcile agents" or "check agents against database"
- When asked to "verify agent registrations" or "audit agent names"
- When asked to "find missing agents" or "find extra agents"
- When asked to "validate naming conventions" or "generate agent fix SQL"
- When asked to "sync agents to database" or "fresh reconciliation"
- **Don't use when:** Creating new agents (use openclaw-ai-agent-creator), managing model assignments (use openclaw-ai-model-assigner), or performing general database operations (use openclaw-ai-sqlite-manager)

## Core Procedures

### Step 1: Schema Validation
1. Query the `openclaw_agents` table schema to verify current columns
2. Compare against expected columns from `schema/create-openclaw-tables.sql`
3. Report any schema mismatches before proceeding

### Step 2: Filesystem Discovery
1. Scan `agent-companies-core/agents/openclawforge-ai/agents/**/AGENTS.md`
2. Parse YAML frontmatter for each agent
3. Extract: `name`, `slug`, `reportsTo`, `role`, `description`, `skills`
4. Build filesystem agent index

### Step 3: Database Discovery
1. Query `openclaw_agents` table → all rows with `id`, `name`, `slug`, `role`, `reports_to`, `description`, `skills`, `company`, `status`
2. Query `openclaw_agent_skills` table → skill assignments by `agent_id`
3. Query `openclaw_agent_models` table → model assignments by `agent_id`
4. Build database agent index

### Step 4: Reconciliation Match
1. Match filesystem agents to database agents by `slug` ↔ `slug`
2. Identify **missing agents**: in filesystem, not in database
3. Identify **extra agents**: in database, not in filesystem
4. Identify **field mismatches**: name, role, reports_to, description differences
5. Identify **missing skill assignments**
6. Identify **missing model assignments**
7. Identify **naming convention violations**

### Step 5: SQL Fix Generation
Generate SQL INSERT/UPDATE/DELETE statements for:
- Missing agents → INSERT into `openclaw_agents`
- Extra agents → DELETE from `openclaw_agents` (with FK cascade)
- Field mismatches → UPDATE `openclaw_agents`
- Missing skills → INSERT into `openclaw_agent_skills`
- Missing models → INSERT into `openclaw_agent_models`

### Step 6: Report Output
- Save SQL to `reconciliation_fixes.sql`
- Save JSON report to `reconciliation_report.json`
- Print summary with counts per table

## Input Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `agents_dir` | string | No | Path to agents directory (default: `agent-companies-core/agents/openclawforge-ai/agents`) |
| `db_path` | string | No | Path to SQLite database (default: `schema/openclaw-app.db`) |
| `output_sql_path` | string | No | Path for SQL output (default: `reconciliation_fixes.sql`) |
| `dry_run` | boolean | No | If true, only report without generating SQL |

## Error Handling

- **Missing agents directory**: Report error and exit
- **Database connection failure**: Report error with connection details
- **Malformed AGENTS.md**: Log warning, skip file, continue
- **No database agents**: Report warning but continue with filesystem scan