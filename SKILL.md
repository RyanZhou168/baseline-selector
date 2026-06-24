---
name: baseline-selector
description: Use when selecting, auditing, or justifying experimental baselines for a research idea, paper draft, task, benchmark, or experiment plan. Finds classic methods, recent SOTA, direct competitors, strong simple baselines, ablation baselines, resource-matched comparisons, and reviewer-expected missing baselines, but only admits baselines with non-empty, accessible GitHub repositories that appear reproducible. Records strong papers without usable open-source code as excluded candidates rather than selected baselines.
---

# Baseline Selector

Use this skill to turn a research idea, task, paper, or experiment plan into a defensible baseline set for experiments and paper submission.

Core rule:

```text
No usable GitHub implementation, no selected baseline.
```

A method may be important, classic, or SOTA, but it cannot enter the recommended baseline set unless its GitHub repository is accessible, non-empty, and plausibly reproducible. Record such methods as excluded candidates with the exclusion reason.

## Modes

Decide the mode from the user request:

1. **Idea to baselines**: user gives a new idea or method sketch.
2. **Task to SOTA**: user asks for baselines for a task, dataset, or benchmark.
3. **Paper audit**: user provides a draft or existing baseline list to check for gaps.
4. **Reviewer-risk check**: user asks what reviewers will say is missing.
5. **Resource-limited selection**: user gives compute/time limits and needs a minimal set.
6. **Reproduction planning**: user already has candidates and needs runnable code choices.

## Output Profiles

Choose an output profile based on the user's real objective. The same task may produce different baseline recommendations under different profiles.

1. **Paper submission mode**: prioritize completeness, reviewer-expected baselines, and stronger defensive coverage.
2. **Fast prototype mode**: prioritize the smallest meaningful runnable set for quick signal.
3. **Limited compute mode**: prioritize budget-compatible baselines and explicitly defer expensive ones.
4. **Industry comparison mode**: prioritize practical open-source systems and deployment-relevant baselines.
5. **Rebuttal emergency mode**: prioritize the missing baselines a reviewer is most likely to demand immediately.

If the user does not specify a profile, infer one from the request and state it explicitly in the report.

## Required Inputs

Proceed with available information, but first infer or ask only for missing details that materially affect baseline scope:

```text
research idea / task:
domain:
dataset or benchmark:
metric:
target venue and year:
compute budget / hardware limit:
time budget:
implementation constraints:
output profile:
```

Target venue is required for final recommendation quality. Examples: `ICML 2027`, `NeurIPS 2028`, `CVPR 2027`, `ACL 2026`.
Compute budget is required for final baseline selection. Ask for GPU type/count, expected run time, and whether the user needs full retraining, fine-tuning only, or inference-only baselines.

If benchmark, metric, or dataset are unknown, state assumptions and mark the baseline set as provisional.

## Response Language Rule

The language of the final user-facing result should follow the language the user uses as closely as possible. Only proper nouns or standard technical names that are not suitable for translation should remain in English.

- Answer body text in the user's language.
- Titles, field names, and decision labels should also follow the user's language whenever practical.
- Proper nouns such as method names, benchmark names, venue names, repository names, and standard technical terms may remain in English when translation would reduce clarity.
- If the user mixes languages, follow the dominant language unless the user explicitly requests bilingual output.
- Do not switch to another language for convenience if the user did not ask for it.
- If a structured report is written to files, the file contents should follow the same rule.

## Main Workflow

0. **Get the current date**
   - Before searching, obtain the current date from the runtime or environment instead of assuming the model's training cutoff.
   - Record `as_of_date`, current year, and freshness windows such as last 6 months, last 12 months, and last 24 months.
   - Use `references/freshness-protocol.md` to decide what counts as recent, latest, or classic.
   - The final report must state the search date and freshness window.

1. **Frame the task**
   - Convert the user request into a precise comparison problem.
   - Identify input, output, dataset, metric, training setting, inference setting, and claim type.
   - Route the task through `references/domain-routing.md` to align the search with field-specific benchmark habits and reviewer expectations.
   - Use `references/search-protocol.md` for search scope and query planning.

2. **Search for candidates**
   - Collect classic methods, direct competitors, recent SOTA, strong simple methods, benchmark official baselines, and reviewer-expected methods.
   - Prefer official benchmark pages, survey papers, same-dataset papers, top-conference papers, leaderboards, arXiv, Papers with Code, and GitHub.
   - Include date-bounded searches for the latest candidates, especially papers and repositories released within the freshness windows.
   - Record the real publication year and venue for every selected or near-selected method, such as `ICML 2025`, `NeurIPS 2024`, or `CVPR 2026`.
   - Track search terms and source types.

3. **Apply the GitHub reproducibility gate**
   - Use `references/github-reproducibility.md`.
   - A selected baseline must have an accessible GitHub repository, non-empty implementation, runnable instructions, dependency/environment notes, and enough code/checkpoints/configs to reproduce or fairly rerun.
   - Exclude papers with missing code, dead links, empty repositories, placeholder repositories, code-only snippets, non-GitHub code dumps, or repositories that cannot reasonably run the claimed method.

4. **Classify baseline roles**
   - Use `references/baseline-taxonomy.md`.
   - Assign each candidate one or more roles: classic anchor, direct competitor, current SOTA, simple strong baseline, resource-matched baseline, practical baseline, ablation baseline, or reviewer-expected baseline.

5. **Build evidence tables**
   - Use `references/evidence-rules.md`.
   - Every candidate needs paper source, real publication year, venue, GitHub source, task match, benchmark/metric match, code status, reproduction risk, and selection decision.
   - Never call a method SOTA unless the task, benchmark, metric, date, and source are explicit.

6. **Select baseline sets**
   - Produce three sets whenever possible:
     - `minimal`: lowest cost set that still makes the comparison meaningful.
     - `standard`: expected paper-quality set for the task.
     - `defensive`: stronger set for top-venue reviewer pressure.
   - Tailor the recommendation to the user's compute budget, time budget, and target venue/year.
   - Tailor the recommendation to the active output profile.
   - In `limited compute mode`, explicitly separate `must run`, `nice to run`, and `too expensive for current budget`.
   - In `rebuttal emergency mode`, prioritize the smallest set of baselines that closes reviewer-visible gaps fastest.
   - Include only GitHub-reproducible candidates in these sets.

7. **Plan reproduction**
   - For each selected baseline, list repository URL, install path, expected data preprocessing, command/config clues, checkpoint availability, expected compute, and main failure risks.
   - Prefer official repositories over unofficial ones unless the official repository is unusable and the unofficial repository is clearly maintained and faithful.

8. **Run reviewer-risk audit**
   - Use `references/reviewer-risk.md`.
   - Identify missing classic methods, missing recent competitors, metric mismatch, split mismatch, compute unfairness, no significance testing, and omitted simple baselines.
   - Separate real risks from risks already handled by excluded non-reproducible methods.

9. **Run self-check**
   - Use `references/self-check.md`.
   - Verify that every selected baseline has the correct year, venue, task match, dataset match, metric match, and GitHub status.
   - Verify that no selected baseline violates the compute budget or target venue strategy.
   - Verify that major expected baseline buckets were considered and that any omitted bucket is explicitly justified.
   - Verify that important non-reproducible or non-matching methods are recorded outside the selected set.

10. **Write final report**
   - Use `templates/baseline-report.md`.
   - If writing files, prefer `baseline_selection/` with numbered outputs.
   - If answering in chat, follow the same section order but keep it concise.

## Output Files

When the user wants files, use this structure:

```text
baseline_selection/
|- 01_task_definition.md
|- 02_search_strategy.md
|- 03_candidate_baselines.md
|- 04_excluded_nonreproducible.md
|- 05_recommended_baseline_sets.md
|- 06_reproduction_plan.md
|- 07_reviewer_risk_check.md
|- 08_self_check.md
`- 09_final_decision.md
```

## Source Label Sets

Choose one source label set at the start of the response and use it consistently.

### English Label Set

Use this set when the user asks in English:

```text
Decision Labels
selected
selected-if-budget-allows
selected-if-run-check-passes
selected-as-harness
excluded-no-github
excluded-empty-repo
excluded-unrunnable-repo
excluded-task-mismatch
excluded-metric-mismatch
excluded-superseded
watchlist
unknown-needs-verification

Final Verdict Labels
strong baseline set
acceptable baseline set
risky baseline set
incomplete baseline set

Section Titles
Task Definition
Search Strategy
Candidate Baselines
GitHub Evidence Chain
Excluded Non-Reproducible or Non-Selectable Candidates
Recommended Baseline Sets
Profile-Aware Recommendation Lens
Minimal Set
Standard Set
Defensive Set
Recommendation for This User
Reproduction Plan
Reviewer Risk Check
Self-Check
Per-Baseline Verification
Coverage Check
Final Verdict
Must Run
Nice To Run
```

### Chinese Label Set

Use this set when the user asks in Chinese:

```text
判定标签
入选
预算允许时入选
运行检查通过后入选
作为辅助框架纳入
因无 GitHub 仓库排除
因空仓库排除
因仓库不可运行排除
因任务不匹配排除
因指标不匹配排除
因已被替代排除
观察名单
待核验

最终结论标签
强 baseline 集合
可接受的 baseline 集合
风险较高的 baseline 集合
不完整的 baseline 集合

章节标题
任务定义
搜索策略
候选 Baseline
GitHub 证据链
排除项与未纳入候选
推荐 Baseline 集合
画像化推荐视角
最小集合
标准集合
防守型集合
面向当前用户的推荐
复现计划
审稿风险检查
自检
逐个 Baseline 核验
覆盖检查
最终结论
必须运行
建议补充
```

Do not output the English source labels directly in a Chinese response unless the label itself is a proper noun or the user explicitly asks for the English wording.

## Final Verdict

Always give one final verdict from the active source label set.

Explain the verdict using:

- coverage of classic anchors;
- coverage of recent SOTA/direct competitors;
- GitHub reproducibility status;
- resource feasibility;
- reviewer risk;
- exact next actions.

## Non-Negotiables

- Always get and record the current date before deciding what counts as latest or recent.
- Always record the real publication year and venue for every selected baseline.
- Always require a target venue/year and a compute budget before finalizing the recommended set.
- Always state the active output profile before recommending the final set.
- Always self-check task fit, benchmark fit, metric fit, venue/year fields, GitHub status, and compute feasibility before the final recommendation.
- Do not recommend a baseline without a usable GitHub repository.
- Do not treat a project page, PDF, leaderboard row, or citation count as reproducible code.
- Do not include empty, placeholder, dead-link, or non-runnable repositories in selected baselines.
- Do not hide non-reproducible SOTA papers; record them in the excluded table with reasons.
- Do not compare methods across incompatible datasets, splits, metrics, or training settings without marking the mismatch.
- Do not claim exhaustive coverage when search evidence is incomplete.

