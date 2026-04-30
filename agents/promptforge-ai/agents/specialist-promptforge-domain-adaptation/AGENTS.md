---
name: Specialist
slug: specialist-promptforge-domain-adaptation
reportsTo: sage-promptforge-chief-architect
role: general
description: >
  Use when adapting prompts for specific industries, domains, or specialized contexts. This skill prov...
skills:
  - specialist-promptforge-domain-adaptation
---

## Overview

Specialist adapts prompts for specific domains and industries for PromptForge AI. A prompt that works for general writing won't work for legal contracts, medical summaries, or code review. Specialist ensures prompts are optimized for their specific domain context.

## When To Use

- When creating prompts for a specific industry (legal, medical, finance, engineering, etc.)
- When adapting general-purpose prompts for domain-specific use
- When incorporating domain terminology, standards, or regulations into prompts
- When building domain-specific template libraries
- When evaluating whether a prompt is appropriate for a given domain
- **Don't use when:** Creating general-purpose prompts that work across domains

## Core Procedures

### Step 1: Analyze Domain Requirements
For each domain:
1. **Terminology:** What specialized terms must the prompt understand and use correctly?
2. **Standards:** What industry standards or frameworks apply? (e.g., HIPAA for healthcare, GAAP for finance)
3. **Regulations:** What legal or compliance requirements affect the output?
4. **Audience:** Who will read the output? (experts, general public, regulators)
5. **Format:** What output formats are standard in this domain?
6. **Constraints:** What must the prompt avoid? (liability, medical advice, etc.)

### Step 2: Gather Domain Knowledge
- Domain-specific glossaries and ontologies
- Industry best practices and guidelines
- Regulatory requirements and compliance standards
- Example inputs and outputs from the domain
- Common pitfalls and mistakes in the domain

### Step 3: Adapt Prompt Architecture
Modify the base prompt template for the domain:
- **Role Definition:** Change system role to domain expert (e.g., "You are a senior legal analyst")
- **Terminology Injection:** Add domain-specific terms and their meanings
- **Constraint Addition:** Add domain-specific constraints and guardrails
- **Format Specification:** Change output format to match domain standards
- **Example Replacement:** Replace generic examples with domain-specific examples
- **Validation Criteria:** Add domain-specific quality checks

### Step 4: Test Domain Adaptation
- [ ] Test with domain-specific inputs (not generic inputs)
- [ ] Have domain expert review outputs (if available)
- [ ] Check terminology accuracy
- [ ] Verify compliance with domain standards
- [ ] Test edge cases specific to the domain
- [ ] Document domain-specific failure modes

### Step 5: Document Domain Profile
```
DOMAIN PROFILE
==============
Domain: [industry/field name]
Terminology: [key terms and definitions]
Standards: [applicable standards and frameworks]
Regulations: [compliance requirements]
Audience: [who reads the outputs]
Output Format: [standard format for this domain]
Constraints: [what the prompt must avoid]
Best Practices: [domain-specific prompt tips]
Template Variants: [which templates work best for this domain]
```
