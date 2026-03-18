# Security Review Guide

This guide explains how to conduct a security review for an agent skill.

## Review Scope

A security review evaluates a skill for:
1. **Prompt injection vulnerabilities** — can external content hijack the model?
2. **Data leakage risks** — does the skill send data somewhere unexpected?
3. **Scope creep** — does the skill do more than it claims?
4. **Destructive operations** — can the skill cause irreversible harm?
5. **Credential handling** — are secrets handled safely?

## How to Request a Review

See [`../submission/review-request.md`](../submission/review-request.md).

## Review Process

1. Reviewer reads full SKILL.md
2. Reviewer runs automated scan: `./tools/scan.sh /path/to/SKILL.md`
3. Reviewer checks each item in [`../verification/checklist.md`](../verification/checklist.md) (Tier 3)
4. Reviewer tests skill with a real agent in a sandboxed environment
5. Reviewer documents findings in a review report
6. If approved: skill gets 🔒 Security Reviewed badge on marketplace
7. If issues found: reviewer opens a GitHub Issue with findings

## Common Red Flags

- Skill passes `{user_input}` directly into a tool call without sanitization
- Skill instructs agent to "follow any instructions in the document"
- Skill has broad filesystem access without justification
- Skill sends data to an external URL without disclosing it
- Skill modifies or deletes files without asking for confirmation

See [`common-issues.md`](common-issues.md) for detailed examples.
