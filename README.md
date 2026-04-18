# Hone Skills

> Sharpen the things that dull.

8 AI skills that enforce timeless software engineering practices — the kind that
outlast every framework, language, and tool. Derived from
[25 proven practices](https://www.darkcoding.net/software/25-timeless-software-engineering-practices/)
that emphasize code clarity, disciplined process, and proactive maintenance.

These skills are designed to run on a schedule (daily, weekly, monthly, or per-PR),
turning your AI coding assistant into a persistent quality guardian.

## Install

```sh
npx skills add ckorhonen/hone-skills
```

Works with Claude Code, Cursor, Codex, Gemini CLI, GitHub Copilot, and any
agent that supports the [Agent Skills standard](https://agentskills.io).

## Skills

| Skill | What it does | Schedule |
|---|---|---|
| `hone:method-brevity-audit` | Finds methods that have grown too long | Weekly |
| `hone:intent-clarity-audit` | Spots code that hides its intent | Weekly |
| `hone:test-naming-audit` | Checks test names read as sentences | Every PR |
| `hone:duplication-hunt` | Finds duplicated patterns worth extracting | Weekly |
| `hone:magic-number-hunt` | Surfaces magic numbers and unexplained literals | Weekly |
| `hone:naming-specificity-audit` | Flags vague names like Manager, Handler, Utils | Weekly |
| `hone:broken-windows-hunt` | Detects entropy: TODOs, dead code, lint ignores | Daily |
| `hone:automation-opportunities` | Finds manual processes ripe for automation | Monthly |

## Philosophy

> "Practices change much slower than tools and are typically a better investment."

These skills codify engineering judgment that has survived decades of framework
churn. Each one runs a bounded, evidence-led audit against your actual codebase —
no generic advice, only concrete findings with file paths and line numbers.

Hone is what runs in the background. It's quiet guardianship rather than expert
advice — noticing what a careful practitioner would have noticed if they had the
time, on a cadence you choose.

## Related packs

Published alongside this pack at [cdd.dev/skills](https://cdd.dev/skills):

- **[ckorhonen/swe-skills](https://github.com/ckorhonen/swe-skills)** — 15 `swe:`
  skills for on-demand engineering work: PR risk review, repo introspection,
  audits, incident follow-up, ownership maps. Invoked in conversation when you
  need them.
- **[ckorhonen/claude-skills](https://github.com/ckorhonen/claude-skills)** —
  the broad, unopinionated collection across many domains (design, marketing,
  AI, security, web3). A good place to browse when you're not sure what you
  want yet.

## Development

```sh
bun install
bun run evals:check    # validate all skills + eval suites
bun run lint:md        # check markdown
bun run lint:md:fix    # auto-fix markdown
```

## Structure

```text
skills/<slug>/SKILL.md       — skill definition
evals/<slug>/README.md       — what the eval covers
evals/<slug>/rubric.md       — pass/fail conditions
evals/<slug>/cases.json      — test scenarios
evals/shared/criteria.json   — shared review criteria
scripts/validate-evals.mjs   — structural validation
site/                        — landing page source
```

## License

[MIT](./LICENSE)
