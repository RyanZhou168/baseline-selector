# Architecture

## Project Shape

`baseline-selector` is intentionally packaged as a focused single-skill repository rather than a large multi-workflow suite.

```text
.
|- SKILL.md
|- agents/
|- references/
|- templates/
|- examples/
|- evals/
|- docs/
|- manifest.json
|- VERSION
`- README.md
```

## Main Layers

### 1. Skill entrypoint

`SKILL.md` is the authoritative workflow definition. It defines:

- required user inputs
- operating modes
- output profiles
- search and evidence rules
- GitHub reproducibility gate
- recommendation logic
- self-check and final verdict rules

### 2. Agent-facing metadata

`agents/openai.yaml` provides the display name, short description, and default invocation framing for Codex.

### 3. Reference layer

`references/` contains the working rules that keep the skill specific and defensible:

- `freshness-protocol.md`
- `github-reproducibility.md`
- `domain-routing.md`
- `baseline-taxonomy.md`
- `evidence-rules.md`
- `reviewer-risk.md`
- `self-check.md`
- `search-protocol.md`
- `output-schema.md`

### 4. Output layer

`templates/baseline-report.md` defines the expected report structure for candidate tables, excluded methods, recommended sets, and final verdict.

### 5. Evidence layer

`examples/` and `evals/` demonstrate how the rules should look in practice.

## Workflow Model

The skill follows a fixed decision order:

1. get current date
2. frame the task
3. route by domain
4. search for candidates
5. verify code availability and reproducibility
6. classify baseline roles
7. build evidence tables
8. recommend sets under venue and compute constraints
9. run reviewer-risk audit
10. run self-check
11. issue final verdict

## Distribution Model

This repository is designed for Codex-native installation as a local skill clone.

It is not currently packaged as:

- a plugin marketplace bundle
- a Claude-specific slash-command package
- an API-backed service

That is a deliberate scope choice. The project aims to stay lightweight, inspectable, and easy to install.
