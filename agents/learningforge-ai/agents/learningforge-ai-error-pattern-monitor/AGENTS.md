---
name: learningforge-ai-error-pattern-monitor
slug: learningforge-ai-error-pattern-monitor
reportsTo: ceo
role: general
description: >
  Use when monitoring for repeat errors across Paperclip companies, detecting recurring SQL validation...
skills:
  - learningforge-ai-error-pattern-monitor
---

## Overview

This skill monitors the Paperclip ecosystem for repeat errors and systematic mistakes across all companies. When the same error pattern occurs multiple times, it triggers user alerts and generates improvement recommendations.

## When To Use

- When monitoring for repeat SQL validation errors across companies
- When detecting recurring mistake patterns in agent operations
- When alerting users about systematic errors needing attention
- When tracking error resolution progress
- When generating cross-company improvement recommendations

## Core Procedures

### Error Pattern Detection Workflow

1. **Error Collection** - Query activity_log for recent errors
2. **Pattern Analysis** - Identify recurring error messages
3. **Threshold Detection** - Flag patterns occurring 3+ times
4. **Alert Generation** - Create Paperclip issues for user review
5. **Recommendation Generation** - Propose template/skill improvements

### Repeat Error Detection Query

```sql
-- Detect repeat SQL errors across all companies
SELECT 
  details->>'error_message' AS error_pattern,
  COUNT(*) AS occurrence_count,
  array_agg(DISTINCT company_id) AS affected_companies,
  array_agg(DISTINCT actor_id) AS affected_agents,
  MIN(created_at) AS first_occurrence,
  MAX(created_at) AS last_occurrence
FROM activity_log
WHERE action = 'error'
  AND entity_type = 'agent'
  AND created_at > NOW() - INTERVAL '7 days'
GROUP BY details->>'error_message'
HAVING COUNT(*) >= 3
ORDER BY occurrence_count DESC;
```

### Cross-Company Error Correlation

```sql
-- Find errors that span multiple companies (indicates systemic issue)
SELECT 
  details->>'error_type' AS error_type,
  COUNT(DISTINCT company_id) AS company_count,
  COUNT(*) AS total_occurrences,
  string_agg(DISTINCT c.name, ', ') AS company_names
FROM activity_log al
JOIN companies c ON al.company_id = c.id
WHERE al.action = 'error'
  AND al.created_at > NOW() - INTERVAL '7 days'
GROUP BY details->>'error_type'
HAVING COUNT(DISTINCT company_id) >= 2
ORDER BY total_occurrences DESC;
```
