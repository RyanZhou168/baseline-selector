# Install and Update

## Overview

This repository is distributed as a single Codex skill.

Install target:

```text
~/.codex/skills/baseline-selector
```

On Windows, that is usually:

```text
%USERPROFILE%\\.codex\\skills\\baseline-selector
```

## Fresh Install

### Windows

```powershell
git clone https://github.com/RyanZhou168/baseline-selector.git "$env:USERPROFILE\.codex\skills\baseline-selector"
```

### macOS / Linux

```bash
git clone https://github.com/RyanZhou168/baseline-selector.git ~/.codex/skills/baseline-selector
```

After installation, open a new Codex conversation. Existing sessions may still use an older skill cache.

## Update an Existing Install

### Windows

```powershell
Remove-Item -Recurse -Force "$env:USERPROFILE\.codex\skills\baseline-selector"
git clone https://github.com/RyanZhou168/baseline-selector.git "$env:USERPROFILE\.codex\skills\baseline-selector"
```

### macOS / Linux

```bash
rm -rf ~/.codex/skills/baseline-selector
git clone https://github.com/RyanZhou168/baseline-selector.git ~/.codex/skills/baseline-selector
```

## Verify the Install

Use a new Codex session and try:

```text
Use $baseline-selector to choose baselines for my AAAI 2027 project.
Task: multimodal retrieval.
Dataset: MSR-VTT.
Metric: R@1.
Compute budget: 4x A100 for 5 days.
```

A successful install should make the skill available by name and route the request through the baseline-selection workflow in `SKILL.md`.

## What Ships by Default

This repository ships:

- the skill entrypoint in `SKILL.md`
- model-facing configuration in `agents/openai.yaml`
- references for reproducibility, freshness, domain routing, reviewer risk, and self-check
- report templates and worked examples
- manual evaluation guidance

## What Is Not Required

This skill does not require:

- extra API keys
- custom MCP setup
- external plugin packaging
- optional scripts to be present for basic use

Codex alone is enough to use the skill.
