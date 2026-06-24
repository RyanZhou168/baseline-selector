# Baseline Selector

[![Version](https://img.shields.io/badge/version-v0.2.0-blue)](VERSION)
[![License](https://img.shields.io/badge/license-MIT-lightgrey)](LICENSE)
[![Install](https://img.shields.io/badge/install-Codex%20skill-black)](docs/INSTALL.md)
[![English](https://img.shields.io/badge/README-English-black)](#english)
[![中文](https://img.shields.io/badge/README-中文-lightgrey)](#中文)

`baseline-selector` 是一个给 Codex 用的 baseline 选择 skill，帮你找 baseline。

## English

### What it does

`baseline-selector` helps you:

- answer in the same language the user uses by default
- search for classic anchors, recent strong methods, and reviewer-expected baselines
- record the real venue and year for selected methods
- reject papers that have no usable GitHub implementation
- separate selected baselines from important but unrunnable exclusions
- recommend different baseline sets under different compute budgets and submission goals
- run a reviewer-risk audit and a final self-check before you commit to the list

### In 30 seconds

| What you give it | What it helps you do |
| --- | --- |
| A research idea | Frame the task, benchmark scope, and baseline buckets |
| A benchmark or task | Find classic, recent, reproducible, and fair baselines |
| A baseline list | Audit gaps, weak comparisons, and fairness issues |
| A submission target | Build a venue-aware set plus reviewer-risk audit |
| A compute budget | Split baselines into must run / nice to run / too expensive |
| Strong papers without code | Record them as exclusions and suggest reproducible substitutes |

### Quick example

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

### Install or update

Fresh install:

```bash
git clone https://github.com/RyanZhou168/baseline-selector.git ~/.codex/skills/baseline-selector
```

Windows PowerShell:

```powershell
git clone https://github.com/RyanZhou168/baseline-selector.git "$env:USERPROFILE\.codex\skills\baseline-selector"
```

Open a new Codex session after installation.

Full install and update instructions: [docs/INSTALL.md](D:/desktop/baselineskill/docs/INSTALL.md)

### Project docs

- [Installation and update](D:/desktop/baselineskill/docs/INSTALL.md)
- [Architecture](D:/desktop/baselineskill/docs/ARCHITECTURE.md)
- [Design principles](D:/desktop/baselineskill/docs/DESIGN_PRINCIPLES.md)
- [Compatibility](D:/desktop/baselineskill/docs/COMPATIBILITY.md)
- [Roadmap](D:/desktop/baselineskill/docs/ROADMAP.md)

### Examples

- [LLM Agent Memory for ICML 2027](D:/desktop/baselineskill/examples/llm-agent-memory.md)
- [3D Detection on nuScenes](D:/desktop/baselineskill/examples/3d-detection-nuscenes.md)

### Repository layout

```text
.
|- SKILL.md
|- agents/
|- references/
|- templates/
|- examples/
|- evals/
|- docs/
|- manifest.json
|- VERSION
`- README.md
```

### Release metadata

- Current version: [`0.2.0`](D:/desktop/baselineskill/VERSION)
- Changelog: [CHANGELOG.md](D:/desktop/baselineskill/CHANGELOG.md)
- Repository metadata: [manifest.json](D:/desktop/baselineskill/manifest.json)
- License: [MIT](D:/desktop/baselineskill/LICENSE)

## 中文

`baseline-selector` 是一个给 Codex 用的 baseline 选择 skill，帮你找 baseline。

它会帮你：

- 默认跟随你的提问语言来回答
- 搜索经典方法、近期强方法和审稿人可能期待的比较对象
- 为入选方法记录真实 venue 和 year
- 把没有可用 GitHub 实现的方法挡在正式 baseline 集合之外
- 区分真正入选的 baseline 和必须记录但跑不了的排除项
- 根据投稿目标和算力预算推荐不同层级的 baseline 集合
- 在最终确定之前做 reviewer-risk audit 和 self-check

### 30 秒看懂

| 你给它什么 | 它帮你做什么 |
| --- | --- |
| 一个 research idea | 帮你定义任务边界、benchmark 范围和 baseline bucket |
| 一个 benchmark 或任务 | 找经典、近期、可复现、可对比的 baseline |
| 一份 baseline list | 检查有没有漏掉关键方法、是否有不公平比较 |
| 一个投稿目标 | 给出更像投稿版的 baseline 集合和 reviewer-risk audit |
| 一个算力预算 | 把 baseline 分成 must run / nice to run / too expensive |
| 几篇很强但没代码的论文 | 记录为排除项，并提供可复现替代方案 |

### 快速示例

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

### 安装与更新

首次安装：

```bash
git clone https://github.com/RyanZhou168/baseline-selector.git ~/.codex/skills/baseline-selector
```

Windows PowerShell：

```powershell
git clone https://github.com/RyanZhou168/baseline-selector.git "$env:USERPROFILE\.codex\skills\baseline-selector"
```

安装后建议新开一个 Codex 会话。

完整安装和更新说明见：[docs/INSTALL.md](D:/desktop/baselineskill/docs/INSTALL.md)

### 项目文档

- [安装与更新](D:/desktop/baselineskill/docs/INSTALL.md)
- [架构说明](D:/desktop/baselineskill/docs/ARCHITECTURE.md)
- [设计原则](D:/desktop/baselineskill/docs/DESIGN_PRINCIPLES.md)
- [兼容性说明](D:/desktop/baselineskill/docs/COMPATIBILITY.md)
- [路线图](D:/desktop/baselineskill/docs/ROADMAP.md)

### 示例

- [LLM Agent Memory for ICML 2027](D:/desktop/baselineskill/examples/llm-agent-memory.md)
- [3D Detection on nuScenes](D:/desktop/baselineskill/examples/3d-detection-nuscenes.md)

### 仓库结构

```text
.
|- SKILL.md
|- agents/
|- references/
|- templates/
|- examples/
|- evals/
|- docs/
|- manifest.json
|- VERSION
`- README.md
```

### 发布信息

- 当前版本：[0.2.0](D:/desktop/baselineskill/VERSION)
- 变更记录：[CHANGELOG.md](D:/desktop/baselineskill/CHANGELOG.md)
- 仓库元信息：[manifest.json](D:/desktop/baselineskill/manifest.json)
- 许可证：[MIT](D:/desktop/baselineskill/LICENSE)
