# grounded-research-skill

> Built by **[Artur Ferreira](https://github.com/arturseo-geo)** @ **The GEO Lab** · [𝕏 @TheGEO_Lab](https://x.com/TheGEO_Lab) · [LinkedIn](https://linkedin.com/in/arturgeo) · [Reddit](https://www.reddit.com/user/Alternative_Teach_74/)

![Version](https://img.shields.io/badge/version-1.0.0-blue)
![Licence](https://img.shields.io/badge/licence-MIT-green)
![Claude Code](https://img.shields.io/badge/Claude_Code-skill-blueviolet)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen)](https://github.com/arturseo-geo/grounded-research-skill/blob/main/CONTRIBUTING.md)

Anti-hallucination research skill for Claude Code. Makes responses shorter and more conservative but dramatically more trustworthy.

Based on [Anthropic's official hallucination reduction techniques](https://docs.anthropic.com/en/docs/test-and-evaluate/strengthen-guardrails/reduce-hallucinations).

## Why This Exists

Claude is excellent at research — but default behaviour optimises for helpfulness, which sometimes means filling gaps with plausible-sounding content rather than admitting uncertainty. This skill flips the trade-off: accuracy over completeness, silence over speculation.

**This is not a default mode.** It significantly constrains creativity. Use it when factual accuracy is non-negotiable.

## The Three Techniques

### 1. Admit Uncertainty

Claude gets explicit permission — and a strict obligation — to say "I don't know" rather than fabricate a plausible answer. Every gap in knowledge is surfaced, not papered over.

### 2. Extract Before Analysing

For any task involving documents or sources, Claude extracts word-for-word quotes first, then builds analysis anchored to those quotes. No analysis without evidence.

### 3. Cite Every Claim

Every factual statement must point to a source or get an explicit "I can't verify this" disclaimer. After generating a response, Claude runs a self-audit — any claim that fails verification is **retracted publicly**, not quietly removed.

## Response Format

Every grounded research response follows this structure:

| Section | Purpose |
|---|---|
| **Sources Consulted** | Every source used, with access method |
| **Key Extractions** | Direct quotes organised by theme |
| **Analysis** | Synthesis with inline citations to extractions |
| **Confidence Assessment** | High / Medium / Low / Unknown per finding |
| **Retractions** | Claims that failed self-audit, with explanation |

## When to Use

- ✅ Fact-checked analysis
- ✅ Document-based Q&A ("based on this document...")
- ✅ Source-verified research
- ✅ Citation-backed answers
- ✅ Any task where accuracy > creativity

## When NOT to Use

- ❌ Creative writing or brainstorming
- ❌ Code generation or debugging
- ❌ Casual conversation
- ❌ Exploratory research (use the [research skill](https://github.com/arturseo-geo/claude-code-skills) instead)
- ❌ Opinion-based or speculative questions

## Install

### Manual install
```bash
git clone https://github.com/arturseo-geo/grounded-research-skill.git ~/.claude/skills/grounded-research
```

### Via skills CLI
```bash
npx skills add arturseo-geo/grounded-research-skill
```

## File Structure

```
grounded-research/
└── SKILL.md    # Complete skill — single file, always loaded
```

This is intentionally a single-file skill. No references directory, no complex structure.
The entire technique fits in one document — adding more files would dilute the constraint.

## How It Works Inside

The skill modifies Claude's behaviour through three complementary constraints:

```
┌─────────────────────────────────────────────────┐
│  1. UNCERTAINTY GATE                            │
│     "Do I actually know this?"                  │
│     If no → say "I don't know"                  │
│     If yes → proceed to extraction              │
├─────────────────────────────────────────────────┤
│  2. EXTRACTION LAYER                            │
│     Pull word-for-word quotes from sources      │
│     These become the ONLY foundation for        │
│     analysis — no quotes, no claims             │
├─────────────────────────────────────────────────┤
│  3. CITATION AUDIT                              │
│     Every claim → must have a source            │
│     No source found → retract publicly          │
│     Retraction is not failure — it's integrity  │
└─────────────────────────────────────────────────┘
```

## Confidence Ratings

| Level | Meaning |
|---|---|
| **High** | Multiple sources confirm, direct quotes support |
| **Medium** | Single source, or inference from strong evidence |
| **Low** | Limited evidence, reasonable inference but unverified |
| **Unknown** | No evidence found — explicitly flagged |

## Contributing

This skill is deliberately minimal. Contributions should keep it that way.

Welcome:
- Improvements to the constraint logic
- Better examples of the technique in action
- Edge case handling

Not welcome:
- Adding reference files (keep it single-file)
- Relaxing the constraints
- Adding features that compromise accuracy for convenience

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

---

## Attributions & Licence

Built and maintained by **[Artur Ferreira](https://github.com/arturseo-geo)** · Part of the **[The GEO Lab](https://thegeolab.net)** toolkit.

### Based on

- [Reduce hallucinations](https://docs.anthropic.com/en/docs/test-and-evaluate/strengthen-guardrails/reduce-hallucinations) — Anthropic's official documentation on hallucination reduction techniques
- [Agent Skills specification](https://github.com/anthropics/skills) by Anthropic (Apache 2.0)

All skill content is original writing. MIT licence.

---

Found this useful? ⭐ Star the repo and connect:
[🌐 thegeolab.net](https://thegeolab.net) · [𝕏 @TheGEO_Lab](https://x.com/TheGEO_Lab) · [LinkedIn](https://linkedin.com/in/arturgeo) · [Reddit](https://www.reddit.com/user/Alternative_Teach_74/)

## Changelog

### v1.0.0 (March 2026) — Initial release
Single-file skill implementing Anthropic's three hallucination reduction techniques:
admit uncertainty, extract quotes before analysis, cite every claim with self-audit.

## Licence

MIT — see LICENSE

---

Built and maintained by **[Artur Ferreira](https://github.com/arturseo-geo)** · Part of the **[The GEO Lab](https://thegeolab.net)** toolkit · [MIT License](LICENSE)
