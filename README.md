# Baseline Selector

[![中文](https://img.shields.io/badge/README-中文-black)](#中文版) [![English](https://img.shields.io/badge/README-English-lightgrey)](#english)

## 中文版

把 baseline 选择这件事做得更扎实一点。

`baseline-selector` 是一个 Codex skill，用来把研究想法、任务定义、论文草稿或实验计划，整理成一个更可辩护的 baseline 决策过程。它会搜索经典方法、近期强方法、审稿人可能期待的比较对象，以及实用的开源 baseline，然后先经过 GitHub 可复现门槛，再决定哪些方法真正值得跑。

### 首屏示例

```text
输入：
我有一个 LLM agent memory 的 idea。
目标会议：ICML 2027。
算力预算：4x A100，5 天。
时间预算：2 周。
任务：带工具调用的长程 agent memory。

输出：
- 经典 anchor baselines
- 最新可复现 baselines
- 无代码或不可运行的 SOTA 排除项
- 考虑算力约束的推荐集合
- reviewer-risk audit
- 最终 baseline 决策前的 self-check
```

### 这个项目解决什么问题

很多人选 baseline 的方式其实很混乱，常见情况包括：

- 凭印象挑几篇有名论文
- 直接沿用 related work 里的方法名
- 看 leaderboard 但不检查代码是否真的能跑
- 一口气选太多自己根本跑不完的 baseline
- 忘了审稿人会追问哪些漏掉的比较对象

`baseline-selector` 想把这件事变成一个更规整的流程：

- 先记录真实检索日期和 freshness window
- 为每个入选 baseline 记录真实 venue 和 year
- 先过 GitHub 可复现门槛，再决定是否纳入
- 根据会议目标和算力预算分层推荐
- 显式记录排除项，而不是悄悄略过
- 在最终建议前做 self-check

### 和普通 baseline 选择的区别

#### 常见做法

- citation 驱动
- 新旧范围不清楚
- 不核对 venue/year
- 不验证代码
- 不考虑算力上限
- 没有排除项记录
- 没有 self-check

#### 用 `baseline-selector`

- 带时间戳的检索
- 明确记录 venue 和 year
- GitHub 可复现门槛
- 考虑预算的推荐
- 记录重要但未纳入的方法
- reviewer-risk 审核
- 最终 self-check

### 这个 skill 的独特点

- 没有可用 GitHub 实现，就不能进正式 baseline 集合。
- 每个入选 baseline 都要求真实 publication venue 和 year。
- “latest” 必须以真实日期为准，而不是模糊的模型记忆。
- 最终推荐必须结合目标会议年份和算力预算。
- 仓库可以按 reproducibility quality 打分，而不只是“有代码/没代码”。
- 输出可以按用户画像切换：投稿、快速验证、算力受限、工业对比、rebuttal 紧急模式。
- 搜索会按领域路由，而不是假装所有领域都用同一套 baseline 选择逻辑。
- 对于不能跑但又重要的论文，会记录为排除项，并保留 related work / reviewer 风险信息。

### 需要用户提供的信息

```text
research idea / task
domain
dataset or benchmark
metric
target venue and year
compute budget / hardware limit
time budget
implementation constraints
output profile（可选，但推荐写）
```

目标会议输入示例：

- `ICML 2027`
- `NeurIPS 2028`
- `CVPR 2027`
- `ACL 2026`
- `AAAI 2027`

算力输入示例：

- `4x A100 for 5 days`
- `1x 4090 for 4 days`
- `inference-only for API baselines`

### 输出结构

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

### 快速开始

```text
Use $baseline-selector to choose baselines for my idea.
Target venue: AAAI 2027.
Compute budget: 4x A100 for 5 days.
Time budget: 2 weeks.
Task: long-context multimodal retrieval.
Dataset: MSR-VTT.
Metric: R@1.
Output profile: paper submission mode
```

输出画像示例：

- `paper submission mode`
- `fast prototype mode`
- `limited compute mode`
- `industry comparison mode`
- `rebuttal emergency mode`

### 安装

#### Windows

```powershell
git clone https://github.com/RyanZhou168/baseline-selector.git "$env:USERPROFILE\.codex\skills\baseline-selector"
```

#### macOS / Linux

```bash
git clone https://github.com/RyanZhou168/baseline-selector.git ~/.codex/skills/baseline-selector
```

然后重启 Codex，或者新开一个会话。

### 仓库结构

```text
.
|- SKILL.md
|- agents/
|- references/
|- templates/
|- examples/
|- evals/
`- README.md
```

### 设计原则

- 先证据，后推荐。
- 先 GitHub 可复现，再纳入 baseline。
- 推荐必须结合会议目标和算力预算。
- 明确记录重要但未纳入的方法。
- 最终必须 self-check。

## English

Make baseline selection more rigorous and easier to defend.

`baseline-selector` is a Codex skill for turning a research idea, task, paper draft, or experiment plan into a more defensible baseline-selection process. It searches for classic anchors, recent strong methods, reviewer-expected comparisons, and practical open-source baselines, then filters them through a hard GitHub reproducibility gate before recommending what to actually run.

### First-screen example

```text
Input:
I have an LLM agent memory idea.
Target venue: ICML 2027.
Compute budget: 4x A100 for 5 days.
Time budget: 2 weeks.
Task: long-horizon agent tasks with memory and tool use.

Output:
- classic anchor baselines
- latest reproducible baselines
- excluded no-code or unrunnable SOTA papers
- compute-aware recommendation
- reviewer-risk audit
- self-check before the final baseline decision
```

### What this project is for

Baseline selection often becomes messy in practice. Common patterns include:

- picking famous papers from memory
- reusing method names from a related-work section
- trusting leaderboard rows without checking code
- selecting more baselines than the budget can actually support
- forgetting the comparisons reviewers are likely to ask for

`baseline-selector` tries to turn that into a more disciplined process:

- record the real search date and freshness window
- record the real venue and year for each selected baseline
- pass the GitHub reproducibility gate before selection
- recommend sets that respect venue goals and compute limits
- record excluded candidates explicitly
- run a self-check before the final recommendation

### What makes it different

- No usable GitHub implementation, no selected baseline.
- Every selected baseline records the real publication venue and year.
- "Latest" is tied to a real date, not vague model memory.
- Final recommendations must reflect the target venue/year and compute budget.
- Repositories can be scored by reproducibility quality, not just labeled code/no-code.
- Output can switch by user profile: paper submission, fast prototype, limited compute, industry comparison, or rebuttal emergency.
- Search can route by domain conventions instead of pretending every field chooses baselines the same way.
- Important but unrunnable papers are still recorded as exclusions with related-work and reviewer-risk context.

### Required inputs

```text
research idea / task
domain
dataset or benchmark
metric
target venue and year
compute budget / hardware limit
time budget
implementation constraints
output profile (optional but useful)
```

Venue examples:

- `ICML 2027`
- `NeurIPS 2028`
- `CVPR 2027`
- `ACL 2026`
- `AAAI 2027`

Compute examples:

- `4x A100 for 5 days`
- `1x 4090 for 4 days`
- `inference-only for API baselines`

### Output structure

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

### Quick start

```text
Use $baseline-selector to choose baselines for my idea.
Target venue: AAAI 2027.
Compute budget: 4x A100 for 5 days.
Time budget: 2 weeks.
Task: long-context multimodal retrieval.
Dataset: MSR-VTT.
Metric: R@1.
Output profile: paper submission mode
```

Profile examples:

- `paper submission mode`
- `fast prototype mode`
- `limited compute mode`
- `industry comparison mode`
- `rebuttal emergency mode`

### Installation

#### Windows

```powershell
git clone https://github.com/RyanZhou168/baseline-selector.git "$env:USERPROFILE\.codex\skills\baseline-selector"
```

#### macOS / Linux

```bash
git clone https://github.com/RyanZhou168/baseline-selector.git ~/.codex/skills/baseline-selector
```

Restart Codex or open a new session.

### License

MIT.
