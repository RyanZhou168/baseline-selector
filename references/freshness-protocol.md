# Freshness Protocol

Use this file before searching for recent or SOTA baselines.

## Current Date

Always obtain the current date from the runtime, shell, system prompt, browser, or another live source available in the environment. Do not infer the date from model memory.

Record:

```text
as_of_date:
current_year:
timezone if available:
search_started_at:
```

If the environment provides the current date directly, use it. If not, run a simple date command or use an equivalent live source.

## Freshness Windows

Define windows relative to `as_of_date`:

```text
last_6_months: very recent candidates
last_12_months: latest strong candidates
last_24_months: recent competitive methods
classic: older methods that remain expected anchors
```

For fast-moving fields such as LLMs, agents, diffusion, vision-language models, robotics foundation models, and retrieval-augmented systems, emphasize the last 6-12 months.

For slower-moving or hardware-heavy fields, last 24-36 months may still count as recent, but record the reason.

## Search Requirements

When the user asks for latest or SOTA baselines:

1. Include the current year and previous year in search queries.
2. Search recent arXiv, OpenReview, major conference proceedings, Papers with Code, and GitHub.
3. Check whether the paper has code now, not only whether it promised code at publication time.
4. Prefer repositories with recent commits, releases, or active issue responses when choosing among comparable baselines.
5. Mark stale repositories as higher reproduction risk, not automatically excluded unless they fail the GitHub gate.

## Report Wording

Use explicit freshness wording:

```text
As of <date>, the latest GitHub-reproducible candidates I found are...
```

Avoid:

```text
This is the latest SOTA.
```

unless the search date, benchmark, metric, and source are all clear.

## Staleness Flags

Flag a selected baseline as stale-risk when:

- no meaningful repository activity for several years;
- dependencies pin old CUDA/PyTorch/TensorFlow versions;
- issues report broken installation;
- benchmark has changed substantially since publication;
- newer reproducible methods dominate it on the same metric.

A stale method can still be selected as a classic anchor, but not as a latest SOTA baseline.
