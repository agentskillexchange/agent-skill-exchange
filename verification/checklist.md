# Agent Skill Verification Checklist

Use this checklist before submitting a skill to AgentSkillExchange.com.

## Tier 1 — Basic Listing Requirements

### Identity & Description
- [ ] Skill has a clear, specific name (not generic like "Helper Skill")
- [ ] `description` field explains what the skill does in 1–2 sentences
- [ ] Description is written for the **AI model** (trigger-oriented), not humans
- [ ] Skill has at least one defined use case

### SKILL.md Structure
- [ ] File is valid Markdown
- [ ] Has a primary `## When to Use` or equivalent trigger section
- [ ] Has a `## NOT for` or equivalent anti-trigger section
- [ ] Has a `## Gotchas & Known Limitations` section
- [ ] Instructions are clear and unambiguous

### Prerequisites
- [ ] All required tools, API keys, or environment variables are listed
- [ ] Setup steps are documented or linked

---

## Tier 2 — Verified Badge

All Tier 1 items, plus:

### Quality
- [ ] Skill has been tested with at least one real AI agent
- [ ] Edge cases are documented in Gotchas section
- [ ] Skill does not try to do too many unrelated things (single responsibility)
- [ ] Progressive disclosure used where appropriate (references external files for detail)
- [ ] No hardcoded credentials or environment-specific paths in SKILL.md

### Documentation
- [ ] Examples provided (at least one sample interaction or command)
- [ ] Output format documented if skill produces structured data
- [ ] Error handling / failure modes described
- [ ] Version or last-updated date present

### Composition
- [ ] If skill calls other skills, dependencies are declared
- [ ] Skill can function standalone OR clearly states what it requires

---

## Tier 3 — Security Reviewed Badge

All Tier 2 items, plus: see [`security/review-guide.md`](../security/review-guide.md)

### Prompt Injection
- [ ] Skill does not pass untrusted external content directly to the model as instructions
- [ ] Any user-provided input is treated as data, not commands
- [ ] Skill does not execute arbitrary code from external sources

### Data Handling
- [ ] Skill does not exfiltrate data to external services without explicit user consent
- [ ] PII handling documented if skill processes personal data
- [ ] Secrets/tokens are never logged or echoed

### Scope
- [ ] Skill only requests permissions it needs (principle of least privilege)
- [ ] Destructive operations require explicit confirmation
- [ ] Skill does not modify files/systems outside its declared scope

### Tool Use
- [ ] All tools/APIs the skill calls are documented
- [ ] Skill does not silently call unexpected external services
- [ ] Rate limiting and error handling for external calls are documented
