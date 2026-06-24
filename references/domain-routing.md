# Domain Routing

Use this file during task framing to align the search with field-specific norms.

## Purpose

Different fields use different benchmarks, metrics, baseline buckets, and reviewer expectations. This file helps avoid generic baseline selection that ignores domain habits.

## LLM Agents

- Common benchmark patterns: long-horizon task suites, tool-use benchmarks, memory-heavy agent evaluations.
- Common metrics: task success rate, step efficiency, token cost, failure recovery, tool accuracy.
- Common baseline buckets: no-memory control, sliding-window control, retrieval memory, persistent memory systems, long-context baselines.
- Common mistakes: comparing memory methods against unrelated agent frameworks, mixing closed and open systems unfairly, ignoring cost.
- Reviewer high-frequency asks: simple controls, retrieval baseline, fairness under the same base model and tool setting.

## Multimodal Retrieval

- Common benchmark patterns: MSR-VTT, MSVD, Flickr30k, COCO retrieval.
- Common metrics: R@1, R@5, R@10, MedR, MnR.
- Common baseline buckets: dual-encoder anchors, recent cross-modal methods, lightweight strong baselines, pretraining-heavy recent methods.
- Common mistakes: mixing incompatible pretraining scales or reporting different retrieval splits.
- Reviewer high-frequency asks: same split, same pretraining assumptions, strong simple dual-encoder baseline.

## CV Detection and Segmentation

- Common benchmark patterns: COCO, nuScenes, KITTI, ADE20K, Cityscapes.
- Common metrics: mAP, NDS, IoU, mIoU, AP by scale.
- Common baseline buckets: official benchmark baselines, backbone-matched competitors, recent top-venue methods, lightweight controls.
- Common mistakes: comparing methods with different backbones, input resolution, or training schedule.
- Reviewer high-frequency asks: backbone fairness, schedule fairness, recent official benchmark competitors.

## GNN

- Common benchmark patterns: Cora, Citeseer, PubMed, OGB datasets, graph classification benchmarks.
- Common metrics: accuracy, ROC-AUC, Hits@K, MRR.
- Common baseline buckets: classic message-passing anchors, simple MLP or feature-only baselines, scalable recent methods.
- Common mistakes: evaluating on outdated small datasets only, ignoring simple baselines, mixing transductive and inductive settings.
- Reviewer high-frequency asks: strong simple baseline, OGB-scale evidence, split fairness.

## RL and Offline RL

- Common benchmark patterns: D4RL, Atari, MuJoCo, Procgen, domain-specific simulators.
- Common metrics: normalized return, sample efficiency, success rate.
- Common baseline buckets: behavior cloning anchor, conservative offline RL methods, online RL only when fair, benchmark official baselines.
- Common mistakes: mixing online and offline RL unfairly, ignoring dataset quality, comparing under different interaction budgets.
- Reviewer high-frequency asks: behavior cloning, strongest offline baselines, same dataset and evaluation protocol.

## Recommender Systems

- Common benchmark patterns: MovieLens, Amazon, KuaiRec, MIND, proprietary ranking datasets.
- Common metrics: NDCG, MRR, Recall@K, CTR-related offline metrics.
- Common baseline buckets: collaborative filtering anchors, sequential recommenders, recent contrastive or graph-based methods, simple popularity baseline.
- Common mistakes: metric mismatch, data leakage, weak simple baselines.
- Reviewer high-frequency asks: popularity/simple baseline, same candidate generation setup, fairness in negative sampling.

## Wireless, Systems, and Networking

- Common benchmark patterns: simulator-based evaluations, real trace datasets, ns-3 style comparisons, systems benchmarks.
- Common metrics: throughput, latency, completion time, fairness, energy, packet loss.
- Common baseline buckets: rule-based anchors, optimization-based methods, learning-based recent methods, practical heuristics.
- Common mistakes: comparing on different trace conditions, ignoring runtime overhead, no strong heuristic baseline.
- Reviewer high-frequency asks: practical heuristic baseline, runtime overhead, robustness across trace regimes.

## Medical AI

- Common benchmark patterns: public imaging datasets, clinical tabular datasets, segmentation benchmarks, detection benchmarks.
- Common metrics: AUROC, AUPRC, sensitivity, specificity, Dice, IoU.
- Common baseline buckets: standard clinical ML anchors, modality-specific deep models, recent benchmark leaders, calibration-aware baselines.
- Common mistakes: data leakage, patient-level split errors, over-claiming on tiny datasets.
- Reviewer high-frequency asks: patient-level split correctness, calibration, clinically relevant simple baselines.

## Routing Rule

When the domain is known:

1. Load the matching domain block.
2. Use its benchmark and metric expectations to shape search queries.
3. Use its common mistakes list as an early self-check.
4. Use its reviewer asks to strengthen the defensive baseline set.

When the domain is mixed:

- combine only the relevant blocks;
- do not borrow baselines across fields unless the report explains why the transfer is fair.
