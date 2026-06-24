# Output Schema

Use this file when writing machine-readable or highly structured reports.

## Candidate Record

```yaml
method: ""
year: ""
venue: ""
paper_url: ""
github_url: ""
github_status: ""
reproducibility_score: 0
roles: []
task_match: "exact | close | weak | mismatch"
benchmark_match: "exact | close | weak | mismatch | unknown"
metric_match: "exact | close | weak | mismatch | unknown"
reported_result: ""
reproduction_risk: "low | medium | high | blocked | unknown"
github_evidence:
  repo_exists: "yes | no | partial | unknown"
  repo_nonempty: "yes | no | partial | unknown"
  method_code_present: "yes | no | partial | unknown"
  train_script_present: "yes | no | justified-not-needed | partial | unknown"
  eval_script_present: "yes | no | partial | unknown"
  requirements_present: "yes | no | partial | unknown"
  checkpoint_present: "yes | no | partial | unknown"
  recently_maintained: "yes | no | mixed | unknown"
  issues_show_broken_setup: "yes | no | mixed | unknown"
  paper_to_code_mapping_clear: "yes | no | close | unclear"
selection_label: "selected | selected-if-budget-allows | excluded-no-github | excluded-empty-repo | excluded-unrunnable-repo | excluded-task-mismatch | excluded-metric-mismatch | excluded-superseded | watchlist | unknown-needs-verification"
reason: ""
```

## Report Record

```yaml
as_of_date: ""
current_year: ""
timezone: ""
research_idea_or_task: ""
domain: ""
dataset_or_benchmark: ""
metric: ""
training_setting: ""
inference_setting: ""
target_venue_and_year: ""
compute_budget_or_hardware_limit: ""
time_budget: ""
implementation_constraints: ""
claim_type: ""
output_profile: "paper submission mode | fast prototype mode | limited compute mode | industry comparison mode | rebuttal emergency mode"
profile_reason: ""
search_strategy:
  freshness_windows: []
  sources_used: []
  query_patterns: []
  scope_assumptions: []
  known_blind_spots: []
```

## Baseline Set Record

```yaml
must_run: []
nice_to_run: []
too_expensive_for_current_budget: []
minimal: []
standard: []
defensive: []
excluded_nonreproducible: []
watchlist: []
final_verdict: "strong baseline set | acceptable baseline set | risky baseline set | incomplete baseline set"
```
