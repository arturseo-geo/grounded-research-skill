# Contributing to grounded-research-skill

Thanks for helping keep this skill accurate and effective. This is a deliberately
minimal, single-file skill — contributions should preserve that simplicity.

## What We Welcome

### ✅ High-value contributions
- **Constraint improvements** — better ways to enforce the three techniques
- **Edge case handling** — scenarios where the current constraints produce poor results
- **Format refinements** — improvements to the response structure or confidence rating system
- **Documentation** — clearer examples, better explanations of when to use vs. not use

### ❌ What we don't accept
- Adding reference files (this is intentionally a single-file skill)
- Relaxing the constraints to make responses "more helpful"
- Adding features that compromise accuracy for convenience
- Changes that would make this trigger on general research tasks

---

## How to Contribute

### 1. Check existing issues first
Someone may already be tracking the change you spotted.
→ [Open Issues](https://github.com/arturseo-geo/grounded-research-skill/issues)

### 2. Fork and create a branch
```bash
git clone https://github.com/YOUR_USERNAME/grounded-research-skill.git
cd grounded-research-skill
git checkout -b improve/retraction-logic
```

### 3. Make your changes
- Keep edits focused — one improvement per PR
- Test the constraint change by running a research task with and without the change
- Explain why the change improves accuracy in your PR description

### 4. Submit a Pull Request
We review all PRs within 7 days.

---

## Design Principles

Before contributing, understand the core trade-off:

> This skill intentionally sacrifices creativity and completeness for accuracy.
> Every change should maintain or strengthen that trade-off.

- **Shorter is better** — if a constraint can be expressed in fewer words without losing precision, do it
- **Single file** — all logic lives in SKILL.md. No references directory, no complex structure
- **Conservative by default** — when in doubt, the skill should say less, not more

---

## Code of Conduct

Be accurate, be useful, cite your sources. That's it.

---

## Questions?

Open a [Discussion](https://github.com/arturseo-geo/grounded-research-skill/discussions)
or reach out via [𝕏 @TheGEO_Lab](https://x.com/TheGEO_Lab).
