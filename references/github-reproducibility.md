# GitHub Reproducibility Gate

Use this file before any candidate is selected.

## Evidence Chain Fields

Collect these fields explicitly when inspecting a repository:

```text
repo_exists:
repo_nonempty:
method_code_present:
train_script_present:
eval_script_present:
requirements_present:
checkpoint_present:
recently_maintained:
issues_show_broken_setup:
paper_to_code_mapping_clear:
```

Interpretation:

- `repo_exists`: the GitHub URL resolves to a real public repository.
- `repo_nonempty`: the repository contains actual source or notebook assets beyond a shell README/license.
- `method_code_present`: the implementation clearly corresponds to the claimed method, not just utilities or data files.
- `train_script_present`: there is a visible training entry point, config, or pipeline.
- `eval_script_present`: there is a visible evaluation entry point, benchmark script, or inference harness.
- `requirements_present`: dependencies, environment, or install instructions are documented.
- `checkpoint_present`: checkpoints, model weights, or explicit guidance to reproduce without them are available.
- `recently_maintained`: the repository is not obviously abandoned relative to the field's pace.
- `issues_show_broken_setup`: issue history indicates whether users repeatedly fail to run the repo.
- `paper_to_code_mapping_clear`: it is clear that the repository matches the specific paper/method under comparison.

These fields turn GitHub inspection into an auditable evidence chain instead of a vague yes/no judgment.

## Hard Gate

A method can enter `minimal`, `standard`, or `defensive` baseline sets only if all required conditions are satisfied:

```text
accessible GitHub URL: yes
repository non-empty: yes
method implementation present: yes
README or run instructions: yes
dependencies or environment described: yes
license or usage clarity: yes or acceptable for research reproduction
dataset / preprocessing guidance: yes or inferable
training or evaluation entry point: yes
```

If any required condition fails, exclude the method from selected baseline sets and record it in the excluded table.

In addition, a method must have `reproducibility_score >= 3` to enter the selected baseline sets.

Minimum field expectations for a normally selectable baseline:

```text
repo_exists: yes
repo_nonempty: yes
method_code_present: yes
train_script_present: yes or justified not-needed
eval_script_present: yes
requirements_present: yes
checkpoint_present: preferred, but not mandatory if rerun path is clear
paper_to_code_mapping_clear: yes
```

If `issues_show_broken_setup = yes`, downgrade reproducibility score unless there is clear evidence the breakage is fixed.

## Repository Status Labels

Use one status label per candidate:

```text
github-verified-official
github-verified-unofficial
github-accessible-needs-run-check
github-empty-or-placeholder
github-dead-link
github-no-implementation
github-no-run-instructions
github-non-github-code-only
github-unknown
```

Only the first three can be considered for selection, and `github-accessible-needs-run-check` should carry reproduction risk.

## Official vs Unofficial Code

Prefer official code. Use unofficial code only when:

- the official repository is absent or unusable;
- the unofficial repository clearly implements the method;
- the repository has enough documentation to run;
- the paper-method mapping is clear;
- the final report marks it as unofficial.

## Empty or Placeholder Repository Signals

A repository also fails the practical reproducibility check when it exists but lacks the field combination needed to rerun the method with confidence.

Exclude if the repository has any of these patterns:

- only README, license, or citation files;
- says "code coming soon";
- no source code for the method;
- no training/evaluation script or notebook;
- broken install instructions with no obvious recovery;
- project page without code;
- GitHub issue history showing the code was never released.

## Reproduction Risk Levels

Use these labels:

```text
low: official, documented, configs/checkpoints available, active or stable
medium: code exists but setup or data processing needs work
high: code exists but sparse docs, old dependencies, missing checkpoints, or unclear settings
blocked: cannot run or cannot identify implementation
```

## Reproducibility Score

Score each candidate from 0 to 5:

```text
5: official repository, clear README, train/eval path, requirements, checkpoints or configs, and direct rerun path
4: official repository with usable instructions, but environment or data setup still needs work
3: unofficial or partially documented repository that still appears faithful and runnable
2: code exists, but implementation is incomplete, fragile, or only partly matches the paper
1: repository shell only, placeholder code, or unclear method mapping
0: no usable code
```

Typical field patterns by score:

- `5`: all core fields are `yes`, maintenance looks healthy, and issue history does not show unresolved breakage.
- `4`: all hard fields are `yes`, but checkpoints or environment setup are weaker.
- `3`: core implementation exists and maps to the paper, but some supporting fields are weaker or unofficial.
- `2` or below: at least one important field is missing, unclear, broken, or misleading.

Selection rule:

```text
reproducibility_score >= 3 -> selectable if other gates pass
reproducibility_score < 3 -> excluded from selected baseline sets
```

Selected baselines should not be `blocked`. A `high` risk baseline can be selected only if it is essential and no better reproducible substitute exists.

When two methods are otherwise comparable, prefer the higher reproducibility score.

## Excluded Candidate Record

For every important excluded method, record:

```text
method:
paper/source:
claimed relevance:
github status:
reproducibility score:
exclusion reason:
possible substitute:
what would make it selectable:
```
