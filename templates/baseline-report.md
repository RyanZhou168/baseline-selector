# Baseline Selection Report

If the user asks in Chinese, convert user-facing section titles, field names, and decision labels into natural Chinese whenever practical. Keep only proper nouns or standard technical names in English when translation would reduce clarity.

Recommended Chinese label mappings for Chinese requests:

```text
Task Definition -> 任务定义
Search Strategy -> 搜索策略
Candidate Baselines -> 候选 Baseline
Excluded Non-Reproducible or Non-Selectable Candidates -> 排除项与未纳入候选
Recommended Baseline Sets -> 推荐 Baseline 集合
Recommendation for This User -> 面向当前用户的推荐
Reproduction Plan -> 复现计划
Reviewer Risk Check -> 审稿风险检查
Self-Check -> 自检
Final Verdict -> 最终结论
selected -> 入选
selected-if-budget-allows -> 预算允许时入选
watchlist -> 观察名单
unknown-needs-verification -> 待核验
acceptable baseline set -> 可接受的 baseline 集合
```

## 1. Task Definition

```text
as_of_date:
current_year:
timezone:
research idea / task:
domain:
dataset / benchmark:
metric:
training setting:
inference setting:
target venue and year:
compute budget / hardware limit:
time budget:
implementation constraints:
claim type:
output profile:
```

## 2. Search Strategy

- Freshness windows used:
- Search sources used:
- Query patterns used:
- Scope assumptions:
- Known blind spots:

## 3. Candidate Baselines

| Method | Venue+Year | Role | Task Match | Benchmark Match | Metric Match | GitHub Status | Repro Score | Reproduction Risk | Decision |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |  |  |  |  |

### GitHub Evidence Chain

| Method | Repo Exists | Repo Nonempty | Method Code | Train Script | Eval Script | Requirements | Checkpoints | Maintained | Broken Issues | Paper-Code Match |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |  |  |  |  |  |

## 4. Excluded Non-Reproducible or Non-Selectable Candidates

| Method | Venue+Year | Paper Importance | GitHub Status | Repro Score | Why Not Selected | Cite in Related Work | Closest Reproducible Substitute | Would Reviewer Ask for It |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |  |  |  |

## 5. Recommended Baseline Sets

### Profile-Aware Recommendation Lens

```text
active output profile:
why this profile was chosen:
how it changes the recommendation:
```

### Minimal

| Method | Venue+Year | Why Included | Estimated Cost |
| --- | --- | --- | --- |
|  |  |  |  |

### Standard

| Method | Venue+Year | Why Included | Estimated Cost |
| --- | --- | --- | --- |
|  |  |  |  |

### Defensive

| Method | Venue+Year | Why Included | Estimated Cost |
| --- | --- | --- | --- |
|  |  |  |  |

## 6. Recommendation for This User

```text
must run:
nice to run:
too expensive for current budget:
recommended set for this user:
why this set fits the target venue:
why this set fits the compute/time budget:
what was intentionally left out:
```

## 7. Reproduction Plan

| Method | GitHub URL | Official/Unofficial | Repro Score | Checkpoints | Main Run Path | Expected Compute | Main Risks |
| --- | --- | --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |  |  |

## 8. Reviewer Risk Check

- Missing classic anchors:
- Missing recent strong methods:
- Missing simple baselines:
- Fairness risks:
- Non-reproducible papers that should still be cited:
- Overall reviewer-risk level:

## 9. Self-Check

### Per-Baseline Verification

| Method | Venue+Year Correct | Task Fit | Benchmark Fit | Metric Fit | GitHub Checked | Compute Fit | Pass/Fail |
| --- | --- | --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |  |  |

### Coverage Check

| Bucket | Status | Notes |
| --- | --- | --- |
| classic anchors |  |  |
| direct competitors |  |  |
| recent/latest methods |  |  |
| simple strong baselines |  |  |
| official benchmark baselines |  |  |
| resource-matched methods |  |  |
| reviewer-expected methods |  |  |

## 10. Final Verdict

```text
final verdict:
ready for experiments:
highest-risk omission:
next 3 actions:
```
