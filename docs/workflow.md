# Draft workflow contract

The parent helps the child improve using public evidence, then tests the frozen strategy against reserved evidence. Keeping hidden feedback out of development prevents the child from adapting to the very cases meant to assess transfer.

## Ownership and visibility

| Item | Parent | Child |
| --- | --- | --- |
| Objective, input/output contract, metric, success criterion and resource budget | Defines with requester; shares before development | Reads and follows |
| Public development cases, baseline and development command | Reviews and coaches from them | Runs, extends within scope and reports |
| `lockin val` cases, labels, evaluator secrets and private evaluation records | Seals and retains under existing access controls | Cannot read or query |
| Strategy, source and canonical output artifact | Reviews the submitted candidate | Authors and freezes |
| Candidate lock and final sanitized result | Records and reports | Submits lock request; receives result after evaluation |
| Accepted source integration, if requested | Owns integration and verification | Corrects source before lock; never publishes the parent target |

The success criterion and metric are public. The reserved examples and answers are hidden. Do not withhold a requirement and later fail the child for never satisfying it.

All native comments, issue descriptions, attachments, project resources and Git history available to the child are public for this workflow. A parent issue is not automatically private. Keep hidden material out of these surfaces, child-bound skill archives, shared logs and shared checkouts. A Git worktree is not an access boundary because it shares repository objects.

Use a parent-only execution environment or an existing evaluator service whose inputs and credentials are inaccessible to the child. Candidate code runs with only the task's allowed inputs and resources, without parent credentials or arbitrary access to the hidden corpus. The evaluator retains labels and captures outputs without feeding logs or per-case answers back to the child during development. Use the supplied evaluation boundary; do not build a new sandbox for this draft. If it cannot support this separation, stop before dispatch and explain the missing prerequisite.

## Before Phase 1: seal the research contract

1. Agree on the public question, distribution or task family, allowed inputs and resources, development evidence, unchanged evaluation command, success criterion, canonical submission path and deadline. Reuse a supplied benchmark's partitions and evaluator. Otherwise reserve representative evaluation cases before development rather than selecting favorable cases afterward.
2. The parent seals the hidden cases and answers and records their existing dataset revision or fixed selection, evaluator version, command and criterion in a private record. Keep them unchanged for this attempt. Share an opaque attempt identifier and the public contract, never private contents or locations.
3. Check the child's effective access to the repository, files, CLI records and evaluation endpoint. If either role shares credentials that expose hidden material, establish an existing protected evaluation route before continuing. Instructions to ignore readable answers are only a cooperation rule, not verified concealment.
4. Create one research child with a self-contained public description and the selected Researcher identity. Include scope, public inputs, commands, deliverable, deadline and candidate-lock procedure. Do not dispatch additional children merely to obtain more hidden scores.

## Phase 1: develop a strategy together

The child first produces a valid baseline using public development inputs and the existing submission contract. Preserve that checkpoint before refinement. Report the proposed mechanism, the public evidence supporting it and its likely limits.

The parent reviews the strategy, source and public results. It can ask the child to test a claimed mechanism, propose public counterexamples, compare on available development inputs or remove an unjustified special case. Advice must follow from the public question and public evidence. Do not paraphrase hidden failures, invent public examples copied from hidden cases or expose a hidden score as a coaching signal.

The child revises in the same issue and keeps the best valid public checkpoint within the agreed budget. Public evidence should probe the stated generalization claim: for example, whether a parser handles unseen documents of the declared format rather than memorizing known strings. Do not require unrelated experiments or invent a scoring rubric.

The parent may return an incomplete strategy or artifact for correction during this phase. Public functional review must finish before the lock. Native comments carry the bounded corrections and evidence; read the relevant threads instead of copying full histories into each handoff.

## The lock: cross the phase boundary

The child submits a lock request naming the exact source commit, strategy and configuration, dependency/environment specification, canonical artifact when applicable, development result and exact reproduction command. Freeze seeds or selection rules when they affect the candidate. Use ordinary Git revision identity; no new checksum scheme is required.

The parent confirms that the candidate is runnable, satisfies the public artifact contract and has not accessed the hidden evidence. It records the accepted lock in the native thread using public fields such as:

```json
{
  "attempt": "parser-transfer-1",
  "candidate_commit": "<exact submitted Git commit>",
  "artifact": "<canonical repository-relative submission path, if applicable>",
  "strategy": "<frozen strategy/configuration reference>",
  "development_evidence": "<public evidence reference>"
}
```

The parent's private record binds this lock to the sealed evaluation inputs and command. Public records contain no hidden cases, answers or credential-bearing paths. Native identity establishes who requested and accepted the lock; an invocation must never borrow another agent's task ID.

A changed candidate needs a new lock. Before hidden evaluation begins, the parent can return it to Phase 1. After hidden feedback has been released, revising it belongs to a new attempt with fresh untouched evaluation cases. Preserve the previous result.

## Phase 2: evaluate the locked candidate

The parent runs the supplied evaluator against the exact locked source and canonical artifact in the protected execution path. It does not run the child's newest branch by convenience. The hidden dataset, evaluator, metric and criterion remain those sealed before development. If an existing baseline comparison is required, use that declared comparison without changing the evaluator.

This phase evaluates one candidate once and makes no coaching calls based on hidden results. Do not select among siblings, seeds or revisions by repeated hidden scoring. After evaluation finishes, publish the permitted aggregate result and decision. Keep case-level outputs and answers private while the holdout remains reserved.

Distinguish a candidate failure from an evaluator infrastructure failure. A deterministic reproduction of the identical candidate is allowed only to recover a confirmed infrastructure failure with no candidate changes or feedback-driven selection; record the reason and attempts. An observed score or ordinary candidate error is a result, not permission to retry improved code against the same holdout.

If hidden content or useful case-specific feedback reaches the child, preserve the evidence and mark this attempt's evaluation compromised. Do not claim an independent generalization result. A future attempt requires a fresh untouched holdout; withholding the leaked text again does not repair independence.

## Decision and delivery

Report one result in the originating parent thread: the question, locked candidate, public development result, hidden aggregate result when valid, whether the predeclared criterion was met, and the limit of the conclusion. Link public evidence and the child's delivery. The parent retains the private evaluation trace separately. State target misses and compromised evaluations plainly.

Meeting the criterion supports transfer on the reserved task family; it does not establish universal generalization. A clean miss may complete the bounded research attempt as a negative result without being accepted as a successful solution. Further research is a separate decision with a fresh holdout if the old result informed it.

The child submits verified work as `in_review` and awaits parent acceptance. The parent owns acceptance and any requested integration: review the locked commit, integrate that exact source, and run the public integration check. A source change needed after hidden evaluation makes a new candidate; it does not inherit the previous hidden result. Preserve human holds and the target workspace's acceptance policy. Do not mark the parent root `done` unless its owner has authorized that completion.

Runtime progress belongs to the invoking native task; handoffs use permitted comments and mentions. Keep findings, locks, verdicts and final results in native comments, public bindings in configuration, and private evaluation records in the protected parent store. Reconcile an uncertain write before retrying so resumption does not create duplicate children or final receipts.

## Minimal implementation evidence

Use one disposable fixture to exercise installation reuse, separate native identities, public correction, a locked revision and evaluation of that revision. Check that the configured Researcher cannot read the hidden files or CLI records, that no hidden value enters child packages or shared records, and that a moved branch does not change the evaluated candidate. Record one final receipt for either a pass or a miss.

A fixture with simulated access proves only its own script behavior. Before claiming hidden evaluation works in Multica, perform one isolated native trial under the actual configured permissions. Keep that trial separate from existing production projects and services. No live trial or generalization result is claimed by this design draft.
