# Evidence Rules

Use this file to keep baseline selection auditable.

## Required Evidence Fields

For each candidate, collect:

```text
method name:
year:
venue / source:
paper URL or DOI:
GitHub URL:
GitHub status:
task match:
dataset / benchmark match:
metric match:
role:
reported performance if relevant:
code availability:
reproduction risk:
selection label:
selection reason:
```

## SOTA Claim Rules

Call a method SOTA only when all are explicit:

```text
task:
dataset:
metric:
evaluation split:
publication or leaderboard date:
source:
code status:
```

If any field is missing, use weaker wording:

```text
recent strong method
reported high-performing method
leaderboard candidate
SOTA candidate, needs verification
```

## Compatibility Rules

Mark mismatch when candidates differ in:

- dataset version;
- train/validation/test split;
- metric definition;
- pretraining data;
- supervision level;
- input modality;
- inference budget;
- data leakage constraints;
- online vs offline setting;
- synthetic vs real data.

A mismatched method can be discussed but should not be selected unless the report explains how to make the comparison fair.

## Output Discipline

Separate selected and excluded candidates. Do not bury exclusions in prose.

Use concise tables. For long searches, keep only decision-relevant evidence in the final report and save detailed search logs separately.
