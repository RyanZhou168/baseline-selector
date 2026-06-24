# Self-Check

Use this file after drafting the baseline set and before the final report.

## Per-Baseline Verification

For every selected or selected-if-budget-allows baseline, verify:

```text
method name matches the paper: yes/no
real publication year recorded: yes/no
real venue recorded: yes/no
task match is real: exact/close/weak/mismatch
dataset or benchmark match is real: exact/close/weak/mismatch/unknown
metric match is real: exact/close/weak/mismatch/unknown
GitHub URL inspected: yes/no
GitHub status acceptable: yes/no
reproduction risk labeled: yes/no
compute fit for user budget: yes/no
```

If any row fails a hard requirement, move the method out of the selected set and record the reason.

## Set-Level Coverage Check

Verify whether the final recommendation covers the expected buckets:

- classic anchors;
- direct competitors;
- recent or latest strong methods;
- simple strong baselines;
- official benchmark baselines when available;
- resource-matched or budget-compatible methods;
- reviewer-expected methods;
- internal ablations if the user is comparing a new component.

Mark each bucket as:

```text
covered
not applicable
considered but excluded
missing and risky
```

## Omission Check

Ask before finalizing:

1. Did I miss any obvious recent GitHub-reproducible method in the user's target venue band?
2. Did I accidentally include a method from the wrong task, split, metric, or supervision setting?
3. Did I select any method only because it is famous, while it is actually not a fair comparison here?
4. Did I forget to record important excluded papers with no runnable GitHub code?
5. Did I over-select expensive baselines that violate the user's hardware or time limits?

## Venue-Target Check

Adjust recommendation strength based on the user's target venue and year.

Examples:

- For `ICML 2027` or `NeurIPS 2028`, expect stronger coverage of recent methods, reviewer-expected methods, and fairness checks.
- For earlier-stage project validation, a smaller minimal set may be enough.
- For fast-moving fields, target venues in later years imply tighter freshness windows.

## Final Self-Check Summary

End with:

```text
per-baseline verification: pass / partial / fail
coverage check: pass / partial / fail
compute-fit check: pass / partial / fail
venue-target fit: pass / partial / fail
ready for final recommendation: yes / no
```
