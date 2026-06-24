# Baseline Selector

[![中文](https://img.shields.io/badge/语言-中文-lightgrey)](./README.md) [![English](https://img.shields.io/badge/Language-English-black)](./README_EN.md)


Make baseline selection more rigorous and easier to defend.

`baseline-selector` is a Codex skill for turning a research idea, task, paper draft, or experiment plan into a defensible baseline decision. It searches for classic anchors, recent strong methods, reviewer-expected comparisons, and practical open-source baselines, then filters them through a hard GitHub reproducibility gate before recommending what to actually run.

## What makes it different

- No usable GitHub implementation, no selected baseline.
- Every selected baseline records the real publication venue and year.
- "Latest" means latest as of a real date, not vague model memory.
- Final recommendations require a target venue/year and compute budget.
- Repositories can be scored by reproducibility quality, not just labeled code/no-code.
- Output can switch by user profile: paper submission, fast prototype, limited compute, industry comparison, or rebuttal emergency.
- Search can route by domain conventions instead of pretending every field chooses baselines the same way.
- Excluded methods still get recorded when they matter for related work or reviewer expectations.

## Quick start

```text
Use $baseline-selector to choose baselines for my idea.
Target venue: AAAI 2027.
Compute budget: 4x A100 for 5 days.
Time budget: 2 weeks.
Task: long-context multimodal retrieval.
Dataset: MSR-VTT.
Metric: R@1.
Output profile: paper submission mode
```

## Installation

### Windows

```powershell
git clone https://github.com/RyanZhou168/baseline-selector.git "$env:USERPROFILE\.codex\skills\baseline-selector"
```

### macOS / Linux

```bash
git clone https://github.com/RyanZhou168/baseline-selector.git ~/.codex/skills/baseline-selector
```

## License

MIT.
