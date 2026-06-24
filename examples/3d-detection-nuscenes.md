# Example: 3D Detection on nuScenes

## User Request

```text
Use $baseline-selector to choose baselines for a new 3D object detection method on nuScenes.
Target venue: CVPR 2027.
Compute budget: 8x H100 for 3 days, or 8x 4090 for 10 days.
Time budget: 3 weeks.
Metric: mAP and NDS.
```

## Expected Skill Behavior

1. Get the current date and search for recent nuScenes baselines using 2025-2026 freshness windows.
2. Record classic anchors, official benchmark baselines, direct competitors, and recent reproducible SOTA candidates.
3. Write real venue-year fields like `CVPR 2025`, `NeurIPS 2024`, or `ECCV 2026` for selected methods.
4. Reject empty or dead GitHub repositories.
5. Reject methods that are not truly comparable on nuScenes detection.
6. Tailor a standard and defensive set for CVPR-level scrutiny.
7. Run self-check to verify no missing obvious leaderboard methods with usable code.
