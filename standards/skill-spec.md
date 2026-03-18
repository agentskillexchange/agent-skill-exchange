# AgentSkill Specification

Version: 1.0 | Maintained by: AgentSkillExchange.com

## What Is a Skill?

An agent skill is a structured set of instructions that tells an AI agent:
1. **When** to activate (trigger conditions)
2. **What** to do (instructions)
3. **When NOT** to activate (anti-triggers)
4. **What can go wrong** (gotchas)

Skills are delivered to the agent via a `SKILL.md` file loaded into its context.

## Required Fields

| Field | Description |
|-------|-------------|
| Name | Clear, specific skill name |
| Description | 1–2 sentence trigger-oriented description (for the model) |
| When to Use | Explicit trigger conditions |
| NOT for | Explicit anti-triggers |
| Gotchas | Known limitations and failure modes |

## Recommended Fields

| Field | Description |
|-------|-------------|
| Prerequisites | Required tools, keys, env vars |
| Examples | Sample usage |
| References | Links to docs, related skills |
| Version | Last updated date |

## Design Principles

1. **Description is for the model, not humans** — it should tell the AI when to trigger the skill
2. **Single responsibility** — one skill, one job
3. **Progressive disclosure** — put details in reference files, not inline
4. **Gotchas are high-signal** — this section helps the model avoid known failure modes
5. **Composability** — skills should work standalone and as part of chains
