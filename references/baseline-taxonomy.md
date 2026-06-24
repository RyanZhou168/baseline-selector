# Baseline Taxonomy

Use this file to classify candidate baselines by experimental role.

## Roles

- **Classic anchor**: historically important or widely expected method that grounds the comparison.
- **Official benchmark baseline**: method shipped with the benchmark, dataset, or leaderboard.
- **Direct competitor**: method solving the same task with a similar setting, input/output, or claim.
- **Current SOTA**: recent top performer for the same benchmark and metric, with date and source.
- **Strong simple baseline**: simple method that is hard to beat and tests whether the new method is overcomplicated.
- **Resource-matched baseline**: similar parameter count, training data, compute, latency, or inference budget.
- **Practical open-source baseline**: commonly used library/toolkit implementation valued by practitioners.
- **Ablation baseline**: internal variant needed to prove a component matters.
- **Reviewer-expected baseline**: method likely to be requested by reviewers even if not the absolute strongest.

## Selection Heuristic

A good standard set usually contains:

```text
1-2 classic anchors
1 official benchmark baseline when available
2-4 direct competitors
1-3 recent SOTA methods
1 strong simple baseline
necessary ablations
```

A minimal set usually contains:

```text
1 classic or official anchor
1 strongest direct competitor
1 simple baseline
critical ablations
```

A defensive set adds:

```text
recent SOTA methods
reviewer-expected methods
resource-matched comparisons
extra simple baselines
```

## Avoid Bad Baseline Sets

Flag these patterns:

- only weak or outdated baselines;
- only methods from the authors' subfield;
- no simple baseline;
- no direct competitor;
- no recent method after a fast-moving benchmark changed;
- methods using incompatible datasets, splits, metrics, or supervision;
- non-reproducible SOTA papers listed as if they were runnable.
