# Draft workflow contract

Installation defines the experiment in private YAML. MAIN dispatches a Reviewer `exp` sub-issue; Reviewer dispatches a Developer `exp` sub-sub-issue with its installed bubblewrap policy. Reviewer coaches development, owns hidden evaluation and returns one result to MAIN.

## Installation fixes the contract

Use [config.example.yaml](../config.example.yaml) as the input shape. Complete it during README-guided installation, not during a research run. Save resolved absolute paths, the fixed holdout revision/selection, unchanged evaluator command, public baseline and score direction, success criterion, time budget and sandbox policy before dispatch. Validate the existing evaluator and canonical artifact contract rather than adding a new scoring system.

Keep the full YAML, holdout and private evaluation records outside Git, Developer mounts, generated packages and child-readable native records. Only public task/configuration fields enter project descriptions and either issue. The private config belongs to Reviewer; distinct agent IDs and issue nesting alone do not hide files or comments.

Preserve the existing root and distinct Reviewer/Developer identities. Reuse saved answers and successful installation IDs on rerun. Each descendant has exactly the `exp` lifecycle label. Prepare role binding, repository/workdir and sandbox before dispatch; parked issues do not start until ready. Reviewer receives the installed holdout access, while Developer receives the restricted profile; do not blindly inherit Reviewer's filesystem access into Developer.

## Developer bubblewrap launcher

The proposed script reads the installed YAML and constructs an argument vector for `bwrap` without shell interpolation. The same installed policy must cover Developer's agent/tool execution and subprocesses; wrapping only the development benchmark leaves other tools able to read host files.

Start from bubblewrap's empty filesystem. Mount the configured runtime paths read-only, public development data read-only at `/data/public`, and the prepared Developer checkout at `/work` with its necessary public Git storage. Create disposable home and temporary directories. Do not mount the host root, Reviewer home, full installation YAML, holdout or private logs. Resolve mount paths and reject any mount that exposes private material, including through shared Git objects.

Use private user/PID/IPC/UTS namespaces with fresh `/proc` and `/dev`, drop capabilities, clear inherited environment and set only installed environment values. Apply the installed network policy; model transport and native handoffs must work under that policy without an unsandboxed fallback. Close inherited file descriptors except those explicitly needed by the selected runtime. Generate this launch profile once at installation and bind it to the Developer experiment before starting it.

Installation checks the actual selected runtime can read public inputs and write its output but cannot read the holdout, full YAML or Reviewer credentials. A failed bubblewrap or runtime check leaves the experiment undispatched. This is a small launcher using the configured runtime, not a new sandbox service. Bubblewrap's [security guidance](https://github.com/containers/bubblewrap#sandbox-security) and [option reference](https://github.com/containers/bubblewrap/blob/main/bwrap.xml) define the underlying mount/namespace behavior.

## Phase 1: develop on public evidence

Developer starts with a valid public baseline and preserves a usable checkpoint before refining. It implements the strategy and reports the mechanism, development result and likely limits in its own issue.

Reviewer reads the public source and evidence, asks for concrete corrections or public counterexamples, and returns work to the same Developer issue. Advice must follow from public evidence; do not turn hidden cases, failures or scores into hints. Both issues remain experiments throughout this loop.

When ready, Developer submits its exact source commit, strategy/configuration, canonical artifact, public result and reproduction command as `in_review`. Reviewer checks the public contract and records the accepted candidate lock. Configuration fixed at installation remains unchanged; the lock binds that configuration to this candidate. A candidate change before hidden evaluation requires a fresh lock.

## Phase 2: evaluate the frozen candidate

Reviewer runs the predefined evaluator against the exact locked candidate and installed `lockin val`, using the supplied evaluator's input/answer boundary. Candidate code does not receive evaluator credentials or unrestricted access to the holdout answers. Do not use the latest branch tip or select among candidates with repeated hidden scores.

Evaluate once, then release the permitted aggregate result. An infrastructure failure can justify reproducing the identical candidate without changes or feedback-driven selection; record why. An ordinary candidate error or low score is a result. Hidden feedback cannot reopen Phase 1 on the same holdout. Preserve a miss honestly; a new informed attempt needs fresh untouched cases. If hidden evidence leaks, mark this evaluation compromised instead of claiming independence.

## Acceptance and result handoff

Reviewer owns Developer acceptance and any requested integration of the reviewed source, under the target workspace's acceptance policy and human holds. Developer does not mark itself `done`. Changes after hidden evaluation do not inherit the earlier hidden result.

Reviewer delivers its result as `in_review` to MAIN, its direct parent. MAIN accepts the Reviewer experiment. Report the question, locked candidate, public result, permitted hidden aggregate, whether the installed criterion was met and the limit of that conclusion. Keep private cases and traces out of both issue threads. A valid negative research result can finish the bounded attempt without being called a successful solution.

Each role runs under its own native task identity. Comments carry public corrections, locks, verdicts and delivery evidence; configuration carries bindings. Reconcile uncertain writes before retrying so resumption creates neither duplicate children nor duplicate final receipts.

The first implementation check is one disposable nested experiment exercising YAML reuse, sandbox access, public rework, lock, evaluation and result receipt. Simulated script checks do not prove native runtime confinement; verify that boundary in one isolated native trial before claiming it works. This repository currently supplies a draft only.
