# Example: LLM Agent Memory Baseline Selection for ICML 2027

## User Request

```text
Use $baseline-selector to choose baselines for my LLM agent memory idea.
Target venue: ICML 2027.
Compute budget: 4x A100 for 5 days.
Time budget: 2 weeks for baseline preparation.
Task: long-horizon agent tasks with memory and tool use.
Metric: task success rate and total token/API cost.
Implementation constraints: prefer open-source models and runnable GitHub repos.
```

## 1. Task Definition

```text
as_of_date: 2026-06-25
current_year: 2026
timezone: Asia/Shanghai
research idea / task: memory-augmented LLM agent for long-horizon tool-use tasks
domain: LLM agents
dataset / benchmark: long-horizon agent benchmarks with task-success evaluation
metric: task success rate, total cost, and failure recovery quality
training setting: primarily inference-time memory augmentation, optional lightweight adaptation
inference setting: multi-step agent trajectories with tool calls
target venue and year: ICML 2027
compute budget / hardware limit: 4x A100 for 5 days
time budget: 2 weeks
implementation constraints: open-source runnable repos preferred, avoid API-only hidden baselines when possible
claim type: memory design improves long-horizon success under realistic budget
output profile: paper submission mode
```

## 2. Search Strategy

- Freshness windows used: last 6 months, last 12 months, last 24 months, and classic anchors.
- Search sources used: benchmark pages, recent top-conference agent papers, arXiv, Papers with Code, GitHub, and same-task papers.
- Query patterns used:
  - `LLM agent memory GitHub`
  - `long horizon agent memory benchmark GitHub`
  - `agent tool use memory paper code`
  - `ICLR 2025 agent memory GitHub`
  - `NeurIPS 2025 long context agent GitHub`
- Scope assumptions: compare runnable open-source memory methods, simple no-memory controls, and retrieval-style memory baselines.
- Known blind spots: closed API-only agent systems and unreleased industrial baselines may exist but are not selectable.

## 3. Candidate Baselines

| Method | Venue+Year | Role | Task Match | Benchmark Match | Metric Match | GitHub Status | Repro Score | Reproduction Risk | Decision |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| No-memory agent | Control Baseline | simple strong baseline | exact | exact | exact | implementation-in-project | 5 | low | selected |
| Sliding-window memory agent | Control Baseline | classic anchor, simple strong baseline | exact | exact | exact | implementation-in-project | 5 | low | selected |
| MemGPT | arXiv 2023 | practical baseline, reviewer-expected baseline | close | close | close | github-verified-official | 4 | medium | selected |
| Letta / persistent memory agent stack | Open-source system 2024 | practical baseline | close | close | close | github-verified-official | 4 | medium | selected-if-budget-allows |
| LIGHTMEM | GitHub-reproducible recent memory method | direct competitor, recent strong method | close | close | close | github-verified-official | 4 | medium | selected |
| RAG-style retrieval memory agent | Open-source recipe | direct competitor | exact | close | close | github-verified-official | 4 | medium | selected |
| Long-context-only agent baseline | recent strong baseline | direct competitor | close | close | exact | github-accessible-needs-run-check | 3 | high | selected-if-budget-allows |

### GitHub Evidence Chain

| Method | Repo Exists | Repo Nonempty | Method Code | Train Script | Eval Script | Requirements | Checkpoints | Maintained | Broken Issues | Paper-Code Match |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| No-memory agent | yes | yes | yes | yes or justified not-needed | yes | yes | yes | yes | no | yes |
| Sliding-window memory agent | yes | yes | yes | yes or justified not-needed | yes | yes | yes | yes | no | yes |
| MemGPT | yes | yes | yes | justified not-needed | yes | yes | yes | yes | no major unresolved blocker | yes |
| Letta / persistent memory agent stack | yes | yes | yes | justified not-needed | yes | yes | partial | yes | mixed | close |
| LIGHTMEM | yes | yes | yes | yes | yes | yes | partial | yes | no major unresolved blocker | yes |
| RAG-style retrieval memory agent | yes | yes | yes | yes | yes | yes | partial | yes | no | yes |
| Long-context-only agent baseline | yes | yes | partial | no clear training path needed | yes | partial | no | mixed | some setup friction | close |

## 4. Excluded Non-Reproducible or Non-Selectable Candidates

| Method | Venue+Year | Paper Importance | GitHub Status | Repro Score | Why Not Selected | Cite in Related Work | Closest Reproducible Substitute | Would Reviewer Ask for It |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Closed-source frontier memory agent paper | NeurIPS 2025 | high | github-no-implementation | 0 | no usable public implementation | yes | LIGHTMEM or retrieval-memory agent | yes |
| Benchmark leaderboard top entry with dead repo | 2026 leaderboard | medium | github-dead-link | 0 | code unavailable in practice | yes | long-context-only agent baseline | maybe |
| Flashy memory paper with placeholder repo | ICLR 2026 workshop | medium | github-empty-or-placeholder | 1 | repo exists but not runnable | maybe | MemGPT | maybe |
| General agent framework without benchmark fit | 2024 system repo | low | github-verified-official | 4 | tool-use framework is real, but not a task-matched memory baseline | no | none needed | no |

## 5. Recommended Baseline Sets

### Profile-Aware Recommendation Lens

```text
active output profile: paper submission mode
why this profile was chosen: the goal is ICML 2027 submission quality rather than a quick prototype or a rebuttal-only patch
how it changes the recommendation: prioritize reviewer-expected memory baselines, stronger controls, and a standard set that is credible for paper submission
```

### Minimal

| Method | Venue+Year | Why Included | Estimated Cost |
| --- | --- | --- | --- |
| No-memory agent | Control Baseline | proves memory is needed at all | low |
| Sliding-window memory agent | Control Baseline | strong simple baseline | low |
| RAG-style retrieval memory agent | Open-source recipe | direct memory competitor | medium |
| LIGHTMEM | recent reproducible memory method | best recent runnable competitor | medium |

### Standard

| Method | Venue+Year | Why Included | Estimated Cost |
| --- | --- | --- | --- |
| No-memory agent | Control Baseline | indispensable simple baseline | low |
| Sliding-window memory agent | Control Baseline | expected simple memory baseline | low |
| MemGPT | arXiv 2023 | recognizable open-source memory anchor | medium |
| RAG-style retrieval memory agent | Open-source recipe | retrieval-memory comparison | medium |
| LIGHTMEM | recent reproducible memory method | strongest runnable recent competitor | medium |

### Defensive

| Method | Venue+Year | Why Included | Estimated Cost |
| --- | --- | --- | --- |
| No-memory agent | Control Baseline | reviewer-proof basic control | low |
| Sliding-window memory agent | Control Baseline | simple but hard-to-dismiss memory control | low |
| MemGPT | arXiv 2023 | likely reviewer-expected mention and comparison | medium |
| RAG-style retrieval memory agent | Open-source recipe | practical retrieval baseline | medium |
| LIGHTMEM | recent reproducible memory method | current strongest runnable competitor | medium |
| Long-context-only agent baseline | recent strong baseline | separates memory design from brute-force context length | high |
| Letta / persistent memory agent stack | Open-source system 2024 | practical persistent-memory system baseline | high |

## 6. Recommendation for This User

```text
recommended set for this user: standard set
must run: no-memory agent, sliding-window memory agent, RAG-style retrieval memory agent, LIGHTMEM, MemGPT
nice to run: Letta / persistent memory agent stack
too expensive for current budget: long-context-only agent baseline if it materially increases inference cost or wrapper complexity
why this set fits the target venue: strong enough for ICML-style scrutiny without relying on non-reproducible papers
why this set fits the compute/time budget: can be prepared and evaluated within 4x A100 for 5 days if the benchmark scope is controlled
what was intentionally left out: expensive long-context and broader system baselines were pushed to defensive-only because of time and setup cost
```

## 7. Reproduction Plan

| Method | GitHub URL | Official/Unofficial | Repro Score | Checkpoints | Main Run Path | Expected Compute | Main Risks |
| --- | --- | --- | --- | --- | --- | --- | --- |
| No-memory agent | local project baseline | official-for-paper | 5 | yes | disable memory module and rerun benchmark | low | none |
| Sliding-window memory agent | local project baseline | official-for-paper | 5 | yes | keep last-k context only and rerun benchmark | low | context truncation implementation bugs |
| MemGPT | public GitHub repo | official | 4 | yes | adapt benchmark wrapper to MemGPT memory interface | medium | integration friction with benchmark/tool layer |
| RAG-style retrieval memory agent | public GitHub repo or project recipe | official or faithful recipe | 4 | partial | attach vector retrieval memory to same agent loop | medium | retrieval quality sensitive to indexing choices |
| LIGHTMEM | public GitHub repo | official | 4 | partial | run memory module on selected benchmark tasks | medium | benchmark adaptation may require custom wrappers |
| Long-context-only agent baseline | public GitHub repo | unofficial or mixed | 3 | no | increase context budget and rerun without explicit memory | high | costly inference and weak repo ergonomics |
| Letta / persistent memory agent stack | public GitHub repo | official | 4 | partial | map benchmark tasks into persistent-memory framework | high | system integration and task wrapper complexity |

## 8. Reviewer Risk Check

- Missing classic anchors: handled by no-memory and sliding-window controls.
- Missing recent strong methods: partially handled, but closed-source top papers remain citation-only risks.
- Missing simple baselines: no; simple baselines are present.
- Fairness risks: must ensure all baselines share the same base model family, tool set, context budget policy, and benchmark protocol.
- Non-reproducible papers that should still be cited: yes, especially recent closed-source memory-agent papers from 2025-2026.
- Overall reviewer-risk level: medium.

## 9. Self-Check

### Per-Baseline Verification

| Method | Venue+Year Correct | Task Fit | Benchmark Fit | Metric Fit | GitHub Checked | Compute Fit | Pass/Fail |
| --- | --- | --- | --- | --- | --- | --- | --- |
| No-memory agent | yes | exact | exact | exact | yes | yes | pass |
| Sliding-window memory agent | yes | exact | exact | exact | yes | yes | pass |
| MemGPT | yes | close | close | close | yes | yes | pass |
| RAG-style retrieval memory agent | yes | exact | close | close | yes | yes | pass |
| LIGHTMEM | yes | close | close | close | yes | yes | pass |
| Long-context-only agent baseline | yes | close | close | exact | yes | borderline | partial |
| Letta / persistent memory agent stack | yes | close | close | close | yes | borderline | partial |

### Coverage Check

| Bucket | Status | Notes |
| --- | --- | --- |
| classic anchors | covered | no-memory and sliding-window controls |
| direct competitors | covered | retrieval-memory and recent memory methods included |
| recent/latest methods | considered but excluded | latest closed-source papers cited but not selected |
| simple strong baselines | covered | strong controls included |
| official benchmark baselines | considered but excluded | none clearly dominant and runnable across this exact setup |
| resource-matched methods | covered | standard set stays within 4x A100/5-day budget |
| reviewer-expected methods | covered | MemGPT included, non-reproducible papers logged |

## 10. Final Verdict

```text
final verdict: acceptable baseline set
ready for experiments: yes, with the standard set
highest-risk omission: the strongest very recent closed-source memory-agent papers cannot be run and must be cited as excluded
next 3 actions:
1. lock benchmark protocol and base model family for all baselines
2. implement and verify the no-memory and sliding-window controls first
3. run LIGHTMEM and retrieval-memory baselines before attempting defensive-only expensive baselines
```
