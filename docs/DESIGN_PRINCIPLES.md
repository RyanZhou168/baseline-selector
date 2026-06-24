# Design Principles

## 1. Reproducibility before prestige

A method can be famous, recent, or highly cited and still fail baseline selection.
If there is no usable GitHub implementation, it does not enter the selected baseline set.

## 2. Time-aware evidence

The skill must use the real current date when deciding what counts as latest, recent, or classic.
This reduces stale baseline recommendations.

## 3. Venue-aware recommendations

Baseline pressure changes by target venue and year.
A set that is enough for an early prototype may be too weak for AAAI, ICML, NeurIPS, CVPR, or ACL submission.

## 4. Compute-aware decision making

The user should not get a recommendation set that is impossible to run.
The skill therefore separates minimal, standard, and defensive sets and can further split them into must-run, nice-to-run, and too-expensive groups.

## 5. Domain-specific routing

Different research communities expect different benchmark habits, metrics, and comparison families.
The skill routes through field-specific baseline logic instead of forcing a fake universal template.

## 6. Explicit exclusions

Strong but unusable papers are still important.
The skill records them with exclusion reasons, reviewer risk, and reproducible substitutes rather than silently hiding them.

## 7. Self-audited outputs

The final recommendation is not complete until the skill checks:

- venue and year correctness
- task and benchmark fit
- metric fit
- GitHub status
- compute feasibility
- bucket coverage

## 8. Useful in real paper workflows

The goal is not only to produce a pretty list.
The output should be strong enough to support experiment planning, paper writing, reviewer defense, and rebuttal decisions.

## 9. Language follows the user

The skill should answer in the same language the user uses by default.
This keeps the workflow readable and reduces friction during real research discussion.
Technical names may stay in their standard English form when that is clearer, but the surrounding explanation should still follow the user's language.
