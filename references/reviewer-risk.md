# Reviewer Risk Audit

Use this file before finalizing the baseline set.

## Common Reviewer Objections

Check whether a reviewer could say:

- missing classic baseline;
- missing strongest recent method;
- missing direct competitor;
- missing simple baseline;
- missing official benchmark baseline;
- baseline implementation is not reproducible;
- comparison uses different splits or metrics;
- method has more data, compute, parameters, or inference budget;
- no ablation proves the key component;
- no statistical significance or multiple seeds;
- cherry-picked datasets;
- non-reproducible SOTA papers ignored without explanation.

## Risk Labels

Use:

```text
low: unlikely to block acceptance
medium: should address if budget allows
high: likely reviewer complaint
critical: comparison may be rejected as unfair or incomplete
```

## Non-Reproducible SOTA Handling

If a strong paper has no usable GitHub implementation:

1. Record it in `excluded_nonreproducible`.
2. State that it is not selected because it fails the GitHub reproducibility gate.
3. Identify a reproducible substitute if possible.
4. Mention it in reviewer risk if reviewers may expect it.
5. Suggest citing it in related work even if not used as a baseline.

## Final Risk Summary

End with:

```text
blocking risks:
recommended fixes:
acceptable omissions:
excluded but cite in related work:
```
