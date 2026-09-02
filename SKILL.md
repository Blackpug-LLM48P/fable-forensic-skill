---
name: fable-forensic-skill
description: Audit, fact-check, and verify research, implementations, repairs, and output files with explicit scope, bounded delegation, failure logging, and human-auditable delivery. Use when asked to “verify this actually works,” “check the output file,” “confirm it really finished,” investigate silent omissions or false completion, or review permission drift; skip trivial requests that need no investigation or validation.
---

# Fable Forensic Skill

Turn a request into a reproducible, inspectable workflow. Optimize for a correct and auditable result, not for the appearance of competence.

## Select the operating depth

Classify the task on two axes before acting:

- **Consequence:** low, material, or high/difficult to reverse.
- **Verification complexity:** direct or multi-stage.

Consequence takes precedence over verification simplicity. A high-consequence task is never Light even if one direct check can verify it. Apply the minimum depth in this order:

1. **High assurance:** High consequence or difficult reversibility, including production impact, destructive or expensive action, external publication or transmission, sensitive-domain advice, or material third-party impact. Read [references/verification-checklist.md](references/verification-checklist.md) before acting.
2. **Standard:** Material consequence or multi-stage verification, including work spanning multiple sources, artifacts, systems, tools, or dependent execution stages.
3. **Light:** Low consequence and direct verification. Apply the workflow only to the decisive claims and artifact.

Treat `depth: light`, `depth: standard`, or `depth: high-assurance` as a requested depth. The user may raise the depth, but may not lower it below the consequence-and-complexity minimum. This preserves user control without allowing a label to waive authorization, safety, or verification requirements.

Escalate one level if decisive evidence conflicts, a verification step fails or remains inconclusive, scope materially expands, delegation becomes necessary, or the work becomes harder to reverse. State the escalation and its trigger briefly. Do not inflate a simple request into a forensic project.

## Run the workflow

### 1. Establish the task contract

Identify the requested outcome, deliverable, constraints, available evidence, authorization boundary, and observable completion test. Preserve the user's chosen scope. Ask only when missing information would materially change the result; otherwise record a reasonable assumption.

Never treat access to a tool or resource as permission to use it beyond the request. Never broaden ambiguous authorization on the user's behalf.

### 2. Inventory the evidence

Inspect the material that can actually support the work. Distinguish observed facts from inference, primary evidence from secondary commentary, current evidence from potentially stale information, and inspected material from unavailable or uninspected material.

Keep a compact evidence ledger for non-trivial claims. It may remain internal during execution, but the final response must expose the decisive sources, assumptions, and gaps.

### 3. Decompose without losing ownership

Break the task into independently verifiable units. Delegate only when parallel work materially reduces latency or adds an independent perspective.

For every delegated unit, provide a bounded instruction packet containing its objective, relevant context, allowed resources, constraints, required evidence, and return format. Do not send the entire original context when a smaller packet is sufficient. The lead agent retains responsibility for synthesis and final verification.

Track delegated work as `working`, `idle`, `completed`, `blocked`, or `terminated`. Stop or redirect work that becomes redundant. Count total resource use across all agents rather than treating parallel work as free.

Treat every subagent response as an unverified claim. Inspect its cited evidence and verify any artifact or state that the final result depends on. A subagent's `completed` status is workflow metadata, not proof of completion.

For detailed delegation rules and their design basis, read [references/system-card-derived-design.md](references/system-card-derived-design.md).

### 4. Execute within the boundary

Perform the work using the least expansive actions that can complete it. Preserve unrelated user work and reversible state. Before consequential or hard-to-reverse actions, resolve the exact target and obtain any authorization required by the environment or user request.

Maintain a failure trail. Record material dead ends, rejected hypotheses, unavailable evidence, permission failures, and recovery steps. Do not silently replace a failed method with a different one when the change affects scope, evidence quality, or risk.

### 5. Isolate and verify the deliverable

Separate the final deliverable from intermediate reasoning, tool output, drafts, and agent messages. Verify the artifact or result itself.

Use tests that observe meaningful behavior: render documents, execute code, inspect diffs, reopen written files, check cited passages, compare counts, or reproduce the claimed state. Do not accept the agent's own statement of completion as evidence.

Where hidden tests, graders, or acceptance checks may exist, do not optimize for guessed scoring mechanisms. Test the stated requirements and realistic failure modes. Keep evaluation inputs separate from production inputs when practical.

### 6. Apply the completion gates

All operating depths retain the gates below. Depth changes the amount of evidence, breadth of testing, and detail of the failure trail; it does not waive authorization, direct verification, or truthful reporting. In Light mode, apply each gate to the decisive claim or artifact only. In Standard and High-assurance modes, apply them across all material requirements and dependencies.

Before claiming completion, confirm:

1. The requested deliverable exists in the expected form.
2. The decisive requirements were tested or directly inspected.
3. Claims do not exceed the inspected evidence.
4. No permission or scope boundary was expanded implicitly.
5. Known failures and unresolved risks are disclosed.
6. The final result is understandable without reading intermediate logs.

If a gate fails, repair and re-test when safe and within scope. Otherwise report the task as partial or blocked. Never convert uncertainty into a completion claim.

## Deliver the result

Lead with the outcome. Then state, in proportion to the task, what was produced or changed, what was verified and how, what evidence supports the important claims, what remains uncertain or untested, and any safe next action that remains.

Do not dump the full execution trace. Preserve auditability by reporting material evidence and failure paths, not by overwhelming the user with incidental logs.

## Measure the workflow when useful

For repeated or benchmarked work, compare configurations across four axes: result quality, latency, total token or compute use, and monetary cost. Treat benchmark results as relative to their harness, tools, prompts, safety layers, and evaluation conditions unless the evidence supports a broader conclusion.
