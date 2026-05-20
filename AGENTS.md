# Agent Skill Contribution Standards

Every skill in this repository follows the same structure so that autonomous agents and human contributors can discover and invoke them consistently.

## Required structure

```
<skill-name>/
├── SKILL.md       # Machine-readable instructions (frontmatter + body)
├── README.md      # Human-readable quick reference
├── examples/      # Runnable demos
└── resources/     # ABIs, chain constants, configs
```

## SKILL.md frontmatter

```yaml
---
name: skill-name
description: One-line summary used by agents to decide when to invoke this skill.
chains: [arc, giwa, bnb]
---
```

- `name` — kebab-case, matches the directory name.
- `description` — one sentence, present tense, action-oriented.
- `chains` — subset of `[arc, giwa, bnb]`.

## Chain scope

369wallet Agent currently targets three chains:

- **Arc** — Circle's chain. Native USDC, HTTP 402 settlement.
- **Giwa** — Upbit's L2.
- **BNB** — BNB Chain.

Skills MUST declare which chains they support in the frontmatter. Skills that only work on a single chain (for example `x402-payment` on Arc) must still declare the field.

## Writing SKILL.md bodies

Keep them short. Agents read this verbatim — every extra paragraph competes for attention.

Recommended sections:

- `## When to use` — bullet list of triggers.
- `## Capabilities` — public surface, one line per function.
- `## Inputs` / `## Outputs` — the contract.
- `## Notes` — caveats only when necessary.

Move long-form context to README.md.

## Submitting

See [CONTRIBUTING.md](./CONTRIBUTING.md).
