# Developing multica-hidden-test

Read README.md, config.example.yaml and docs/workflow.md. This repository holds a design draft. Implement only when assigned; do not install it into Research or RSI while drafting.

Keep the roles **Reviewer** and **Developer**. The existing MAIN root creates a Reviewer sub-issue labeled `exp`; Reviewer creates a Developer sub-sub-issue labeled `exp`. Reviewer coaches, locks, evaluates and accepts Developer. MAIN dispatches and accepts Reviewer's result. Follow the target workspace's acceptance policy and human holds.

Define all task, holdout, command, metric, criterion, budget and sandbox settings at installation in Reviewer-only YAML. Follow featssship's README-guided install/reuse pattern. Never choose a new holdout during development or copy private configuration into child-readable packages or records.

Use a small script to apply the installed bubblewrap policy to Developer execution before dispatch. Expose only its public inputs, prepared checkout and selected runtime. Preserve the hidden inputs, answers, private YAML and Reviewer credentials outside that boundary. Do not substitute a benchmark-only wrapper for confinement of the Developer's tools.

Phase 1 uses public evidence for corrections. Phase 2 evaluates one exact frozen candidate on installed `lockin val`. No hidden-driven retuning against the same holdout; retain honest misses. Reuse the task's evaluator and canonical artifact contract.

Keep repository-owned procedures atomic, using the current Symbolic-SoP template and native Multica CLI handoffs. Installation is an ordinary script. No submodules or system distribution/review/delivery SOP dependencies. Keep focused checks in tests/ and use one disposable nested trial. Private YAML, generated packages, logs and runtime state stay out of Git.

Use ponytail. Preserve unrelated agents, skills, services and data. Deliver concise evidence with links and distinguish draft design, script checks and live runtime proof.
