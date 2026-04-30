# agent-companies-core

Canonical platform-agnostic definitions for AI agent companies, agents, skills, domain knowledge, projects, and specifications.

Consumed as a git submodule by:

- **agent-companies-paperclip** — Paperclip + Hermes orchestration (preserved)
- **agent-companies-openclaw** — OpenClaw orchestration (active development)

```
├── companies/         COMPANY.md + TEAM.md (16 companies, 29 teams)
├── agents/            AGENTS.md (449 agents, adapter fields stripped)
├── skills/            SKILL.md capability definitions
│   └── shared/        Cross-company skills (85 files)
├── domain-knowledge/
│   ├── disciplines/          50+ engineering/commercial domains
│   ├── shared-disciplines/   Bidding, engineering, measurement, SaaS, testing, voice
│   ├── organisations/        Client knowledge (GPC, Zama)
│   └── disciplines-non/      Admin (travel, timesheets)
├── projects/          ~70 charters + ~479 issue descriptions
├── specs/             UI-UX specifications (78 files)
├── cross-reference/   Canonical teams/rosters cross-reference
├── standards/         Platform-agnostic coding procedures
├── para/              PARA knowledge base (~11k files)
└── packages/db/       Domain database schema + migrations
```

No platform-specific adapter, runtime, or API config belongs here.

Extracted from [paperclip-render](https://github.com/Construct-AI-primary/paperclip-render).