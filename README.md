# AgentSkillExchange — Verification & Security Review

> Open-source framework for verifying and security-reviewing AI agent skills listed on [AgentSkillExchange.com](https://agentskillexchange.com).

[![Marketplace](https://img.shields.io/badge/Marketplace-AgentSkillExchange.com-6366f1)](https://agentskillexchange.com)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)
[![Skills Verified](https://img.shields.io/badge/Skills%20Verified-31-blue)](https://agentskillexchange.com/verified-skills/)

---

## What Is This?

When AI agent skills are submitted to [AgentSkillExchange.com](https://agentskillexchange.com), they go through a structured verification and security review process. This repo is the **open-source home of that process** — the criteria, checklists, tools, and badge definitions are public so:

- **Skill authors** know exactly what reviewers look for
- **Security researchers** can improve the review criteria
- **Enterprises** can run the same checks internally before deploying skills
- **Community** can contribute new checks, flag issues, propose standards

---

## Repository Structure

```
/
├── verification/
│   ├── checklist.md          # Full verification checklist (all tiers)
│   ├── criteria/
│   │   ├── basic.md          # Basic listing requirements
│   │   ├── verified.md       # Verified skill badge criteria
│   │   └── security.md       # Security-reviewed badge criteria
│   └── badges.md             # Badge definitions and what they mean
│
├── security/
│   ├── review-guide.md       # How to conduct a security review
│   ├── threat-model.md       # Threat model for agent skills
│   ├── common-issues.md      # Known security anti-patterns in skills
│   └── tools/
│       └── scan.sh           # Basic automated scan script
│
├── submission/
│   ├── SKILL_TEMPLATE.md     # Standard SKILL.md template
│   ├── submission-guide.md   # How to submit a skill for review
│   └── review-request.md     # Template for requesting a review
│
├── standards/
│   ├── skill-spec.md         # AgentSkill specification
│   ├── categories.md         # Official skill category taxonomy
│   └── quality-gates.md      # Quality gate definitions
│
└── CONTRIBUTING.md
```

---

## Verification Tiers

| Badge | Criteria | What It Means |
|-------|----------|---------------|
| 🟢 **Listed** | Passes basic schema check | Skill exists and has required fields |
| ✅ **Verified** | Passes full checklist | Quality-reviewed, well-documented, tested |
| 🔒 **Security Reviewed** | Passes security audit | Reviewed for prompt injection, data leakage, scope creep |

See [`verification/badges.md`](verification/badges.md) for full definitions.

---

## Quick Start — Self-Review Your Skill

Before submitting to the marketplace, run through the checklist yourself:

```bash
# Clone this repo
git clone https://github.com/gagankcai-jpg/agent-skill-exchange.git
cd agent-skill-exchange

# Review your skill against the checklist
cat verification/checklist.md

# Run the basic automated scan (requires bash)
./security/tools/scan.sh /path/to/your/SKILL.md
```

---

## Skill Template

Use [`submission/SKILL_TEMPLATE.md`](submission/SKILL_TEMPLATE.md) as your starting point when creating a new skill. It follows the [AgentSkill standard](standards/skill-spec.md) and is pre-structured to pass verification.

---

## Contributing

We welcome contributions from the community:

- **New security checks** — spotted a pattern reviewers should look for?
- **Checklist improvements** — missing criteria or outdated items?
- **Category proposals** — think the taxonomy needs a new category?
- **Tool improvements** — better automated scan scripts?

See [CONTRIBUTING.md](CONTRIBUTING.md) to get started.

---

## Marketplace Integration

Skills reviewed using this framework are listed at **[AgentSkillExchange.com](https://agentskillexchange.com)** with their corresponding badges. The marketplace surfaces:

- Verification tier (Listed / Verified / Security Reviewed)
- Review date and version
- Link back to review artifacts (coming soon)

**Submit a skill for review:** [agentskillexchange.com/submit-skill/](https://agentskillexchange.com/submit-skill/)

---

## License

MIT — use this framework however you like, commercially or otherwise. Attribution appreciated.
