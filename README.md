# multica-hidden-test

Draft a standalone Multica research SOP with **Reviewer** and **Developer** roles. Installation fixes the task, hidden `lockin val` and bubblewrap policy in YAML. Reviewer helps Developer build a strategy on public evidence, then evaluates one frozen candidate on the predefined holdout.

**Status: design draft.** Includes the workflow and example configuration. The installer and execution scripts are not implemented.

## Issue tree and two phases

```text
MAIN — existing root: dispatch and receive
└── Reviewer [exp] — sub-issue: coach, lock, evaluate and accept
    └── Developer [exp] — sub-sub-issue: develop inside bubblewrap
```

1. **Develop:** Reviewer coaches Developer using public development results. Developer implements, checks and revises in the same experiment issue.
2. **Evaluate:** Developer freezes its strategy, configuration, exact source revision and canonical artifact. Reviewer runs the predefined evaluator against that candidate on `lockin val`, then reports the result to MAIN.

Both descendant issues carry `exp`, with no `dev` or `query` lifecycle label. Reviewer is Developer's direct parent. MAIN dispatches requests and receives the Reviewer result.

The holdout is fixed **at installation**, before either experiment starts. Hidden results cannot guide revisions against that same holdout. A miss is a research result; further informed development needs a fresh untouched holdout. A finite holdout supports a bounded generalization claim.

## Installation guidance

Follow [multica-featssship's README-guided installation and portable packaging](https://github.com/Winfred666/multica-featssship/tree/e4d8ff30cf8dc10e009034625ef0d198feb94503), using YAML for this product:

1. Copy [config.example.yaml](config.example.yaml) to a Reviewer-only location outside Git and every Developer mount. Fill in the target, existing root, distinct agent IDs, public task, commands, measured baseline, metric, acceptance criterion, budget, fixed holdout and sandbox paths.
2. The future installer asks only for missing answers and saves them to that YAML. It resolves paths and the fixed dataset revision, checks bubblewrap with the selected runtime, and saves reused agent/skill IDs. No experiment starts with unresolved configuration.
3. Preserve the existing root, history and unrelated bindings. Generate the public project/issue context and Developer package from an explicit public field list; never copy the private YAML or `lockin_val` section into them.
4. Generate the Developer launcher from the saved sandbox policy. Check public input access and denied holdout/config access before dispatch. Later runs reuse the saved values without choosing a new holdout or changing its evaluator.

The install contract predefines roles, hierarchy, experiment baseline/direction, data, commands, criterion, budget and sandbox. Candidate revisions, issue IDs and measured results are runtime outputs. Reinstallation reuses successful native writes; a changed holdout defines a new attempt.

## Minimal implementation

Keep one root dispatch SOP, supporting Reviewer/Developer procedures and ordinary install/launch scripts in this repository. Use the current Symbolic-SoP template and native Multica CLI handoffs without submodules or system distribution/review/delivery SOP dependencies.

The launch script translates installed YAML into bubblewrap arguments for Developer execution. Reviewer retains access to `lockin val`; Developer receives only public inputs, its prepared checkout and the selected runtime files. Bind this policy before starting the Developer `exp` sub-sub-issue. See the [workflow contract](docs/workflow.md) for the sandbox and result handoffs.

One disposable trial should show YAML reuse, the two nested `exp` issues, a public correction, denied hidden-data access, an exact candidate lock and one result to MAIN. Keep focused checks under `tests/`. Existing Research/RSI workflows, shared services and historical backups are outside implementation scope.
