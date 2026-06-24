# Compatibility

## Supported Runtime

This repository is written for Codex skill usage.

Expected environment:

- Codex with local skill loading enabled
- a standard local Git installation for clone-based install or update
- normal web access when Codex performs live baseline searches

## Designed For

`baseline-selector` is designed for:

- Codex desktop or local Codex environments that load skills from `~/.codex/skills/`
- research workflows where the agent can read repository files and perform web-backed evidence gathering
- users who want a single-skill install without extra provider-specific setup

## Not Required

This project does not depend on:

- external API keys for normal usage
- plugin marketplace packaging
- custom background services
- a separate orchestration runtime

## Known Scope Boundaries

- The repository is packaged as a single Codex skill, not as a multi-plugin suite.
- Installation guidance assumes clone-based local skill installation.
- Existing Codex sessions may cache an older version of the skill until a new session is opened.
- Search completeness still depends on live web availability and the quality of task framing.

## Compatibility Goal

The goal is practical portability with minimal setup friction, not deep integration with every client or provider.
