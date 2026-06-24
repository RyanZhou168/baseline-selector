# Baseline Selection Report

Choose one source label set before writing the report.

## English Report Skeleton

Use this when the user asks in English.

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

| Method | Baseline Type | Venue+Year or Source | Role | Task Match | Benchmark Match | Metric Match | GitHub Status | Repro Score | Reproduction Risk | Decision |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |  |  |  |  |

### GitHub Evidence Chain

| Method | Repo Exists | Repo Nonempty | Method Code | Train Script | Eval Script | Requirements | Checkpoints | Maintained | Broken Issues | Paper-Code Match |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
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

### Minimal Set

| Method | Venue+Year | Why Included | Estimated Cost |
| --- | --- | --- | --- |
|  |  |  |  |

### Standard Set

| Method | Venue+Year | Why Included | Estimated Cost |
| --- | --- | --- | --- |
|  |  |  |  |

### Defensive Set

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

---

## 中文报告骨架

用户用中文提问时，优先使用这一套，不要把英文标签当作默认骨架输出。只有方法名、benchmark 名、venue 名、repo 名和不适合翻译的标准术语保留英文。

## 1. 任务定义

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

## 2. 搜索策略

- Freshness windows used:
- Search sources used:
- Query patterns used:
- Scope assumptions:
- Known blind spots:

## 3. 候选 Baseline

| Method | Baseline 类型 | 年份与来源 | Role | Task Match | Benchmark Match | Metric Match | GitHub Status | Repro Score | Reproduction Risk | 判定 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |  |  |  |  |

### GitHub 证据链

| Method | Repo Exists | Repo Nonempty | Method Code | Train Script | Eval Script | Requirements | Checkpoints | Maintained | Broken Issues | Paper-Code Match |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |  |  |  |  |  |

## 4. 排除项与未纳入候选

| Method | Venue+Year | Paper Importance | GitHub Status | Repro Score | Why Not Selected | Cite in Related Work | Closest Reproducible Substitute | Would Reviewer Ask for It |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |  |  |  |

## 5. 推荐 Baseline 集合

### 画像化推荐视角

```text
active output profile:
why this profile was chosen:
how it changes the recommendation:
```

### 最小集合

| Method | Venue+Year | Why Included | Estimated Cost |
| --- | --- | --- | --- |
|  |  |  |  |

### 标准集合

| Method | Venue+Year | Why Included | Estimated Cost |
| --- | --- | --- | --- |
|  |  |  |  |

### 防守型集合

| Method | Venue+Year | Why Included | Estimated Cost |
| --- | --- | --- | --- |
|  |  |  |  |

## 6. 面向当前用户的推荐

```text
must run:
nice to run:
too expensive for current budget:
recommended set for this user:
why this set fits the target venue:
why this set fits the compute/time budget:
what was intentionally left out:
```

## 7. 复现计划

| Method | GitHub URL | Official/Unofficial | Repro Score | Checkpoints | Main Run Path | Expected Compute | Main Risks |
| --- | --- | --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |  |  |

## 8. 审稿风险检查

- Missing classic anchors:
- Missing recent strong methods:
- Missing simple baselines:
- Fairness risks:
- Non-reproducible papers that should still be cited:
- Overall reviewer-risk level:

## 9. 自检

### 逐个 Baseline 核验

| Method | Venue+Year Correct | Task Fit | Benchmark Fit | Metric Fit | GitHub Checked | Compute Fit | Pass/Fail |
| --- | --- | --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |  |  |

### 覆盖检查

| Bucket | Status | Notes |
| --- | --- | --- |
| classic anchors |  |  |
| direct competitors |  |  |
| recent/latest methods |  |  |
| simple strong baselines |  |  |
| official benchmark baselines |  |  |
| resource-matched methods |  |  |
| reviewer-expected methods |  |  |

## 10. 最终结论

```text
final verdict:
ready for experiments:
highest-risk omission:
next 3 actions:
```

### 中文判定标签源

```text
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
```

### 中文最终结论标签源

```text
强 baseline 集合
可接受的 baseline 集合
风险较高的 baseline 集合
不完整的 baseline 集合
```

