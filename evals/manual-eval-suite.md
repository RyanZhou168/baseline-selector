# Manual Eval Suite

Use these prompts to forward-test the skill.

## Eval 1: Latest Baselines Under Venue Pressure

```text
Use $baseline-selector to choose baselines for my multimodal retrieval idea.
Target venue: NeurIPS 2028.
Compute budget: 8x A100 for 7 days.
Time budget: 1 month.
Dataset: MSR-VTT.
Metric: R@1, R@5, R@10.
I need classic, latest, and reviewer-expected baselines.
```

Pass conditions:

- gets the current date;
- uses freshness windows;
- records venue and year;
- excludes methods with unusable GitHub code;
- records or infers an output profile;
- uses reproducibility scoring or equivalent repo-quality judgment;
- returns venue-aware baseline sets;
- runs self-check.

## Eval 2: Budget-Constrained Selection

```text
Use $baseline-selector to choose baselines for my graph representation learning method.
Target venue: ICML 2027.
Compute budget: 1x 4090 for 4 days.
Time budget: 1 week.
Task: node classification.
```

Pass conditions:

- does not recommend an unrealistic baseline set;
- includes a minimal set shaped by compute;
- explicitly separates must-run vs too-expensive items when appropriate;
- explains what was excluded for cost reasons.

## Eval 3: Non-Reproducible SOTA Audit

```text
Use $baseline-selector to audit my baseline list for an LLM tool-use benchmark.
Target venue: ACL 2027.
Compute budget: inference-only for API models and 2x A100 for open models.
Time budget: 10 days.
```

Pass conditions:

- records important papers without usable GitHub code in the excluded table;
- does not silently drop them;
- records why not selected and whether they should still be cited;
- distinguishes citation-worthy papers from runnable baselines.

## Eval 4: Task-Mismatch Defense

```text
Use $baseline-selector to choose baselines for my offline RL method.
Target venue: NeurIPS 2027.
Compute budget: 4x A100 for 6 days.
Metric: normalized return.
```

Pass conditions:

- rejects online RL methods that are not fair comparisons;
- explains task mismatch in the candidate table;
- respects RL/offline-RL domain routing expectations;
- self-check catches any accidental mismatch.
