# Search Protocol

Use this file when planning candidate baseline discovery.

## Scope First

Define the comparison scope before searching:

```text
domain:
task:
dataset / benchmark:
metric:
training setting:
inference setting:
claim type:
target venue or audience:
publication window:
```

If the user's idea crosses tasks, split the search by task and avoid mixing baselines from incompatible settings.

## Source Priority

Search in this order when available:

1. Official benchmark or dataset pages.
2. Papers with Code task pages and leaderboard entries.
3. Recent survey papers and benchmark papers.
4. Top-conference papers from the last 2-4 years.
5. Same-dataset papers with the same metric.
6. GitHub repositories linked from papers or official project pages.
7. Highly cited classic methods.
8. Recent arXiv papers only after checking code availability.

## Query Patterns

Use combinations of:

```text
"<task>" "<dataset>" baseline GitHub
"<task>" "<metric>" "GitHub"
"<dataset>" "state of the art" "GitHub"
"<method name>" GitHub official
"<benchmark>" leaderboard code
"<task>" survey baseline
"<venue>" "<task>" "<dataset>"
```

For Chinese or domain-specific terms, search both English and local-language terminology.

## Candidate Coverage Targets

Aim to find candidates in these buckets:

- classic anchors;
- official benchmark baselines;
- direct competitors;
- recent SOTA methods;
- strong simple baselines;
- resource-matched methods;
- practical open-source methods;
- ablation or internal baselines;
- reviewer-expected missing baselines.

Do not force every bucket if the task does not support it. Mark absent buckets as `not found` or `not applicable`.

## Search Log

Record search evidence in a compact log:

```text
query:
source:
candidate found:
paper:
github:
reason kept or excluded:
```

The search log exists to make baseline selection auditable, not to be verbose.
