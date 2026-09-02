# System-card-derived design notes

## Purpose and limits

These notes translate selected findings and evaluation methods from the *Claude Fable 5.1 & Claude Mythos 5.1 System Card* into conservative workflow controls. They are design inspiration, not an Anthropic-authored skill, an official implementation, or a claim that the benchmark results generalize to every agent environment.

Page references below refer to the original English page numbers in the system card.

## Controls adopted by this skill

### Isolate the deliverable from the trace

The DRACO evaluation instructed the model to write its complete final report to a file and graded only that file rather than the full agent transcript (p. 179). This separates the user-facing artifact from intermediate tool noise.

**Skill rule:** Validate the final artifact directly. Intermediate reasoning, messages, and successful tool calls do not prove the deliverable is correct.

### Delegate with scoped context

In the asynchronous-subagent harness, each subagent receives instructions from the lead rather than the original task description (p. 183). The lead retains direct access to task tools and receives subagent results as messages.

**Skill rule:** Give a subagent the smallest context packet that preserves its objective, constraints, evidence requirements, and return format. The lead owns synthesis and verification.

### Track lifecycle and reclaim concurrency

The same harness exposes subagent status and allows the lead to create or delete subagents, freeing concurrency slots (p. 183).

**Skill rule:** Track useful working state, terminate redundant work, and do not leave parallel jobs running without a role in the final result.

### Treat parallelism as a tradeoff

On 166 selected ProgramBench tasks, both a fixed five-agent team and asynchronous subagents reached a given score faster than the single-agent baseline, while using additional token budget. The fixed team reached a score of 0.6 at roughly twice the speed of the single agent in that harness; asynchronous subagents later achieved the highest final score (pp. 180-182). The report explicitly frames this as a latency-cost tradeoff.

**Skill rule:** Parallelize bounded independent work when latency or independent coverage matters. Do not claim that more agents are universally better. Measure total resource use across the whole task.

### Compare the harness, not an imagined universal model

The multi-agent methodology compares score, derived latency, aggregate token use, and cost. The report cautions that the ProgramBench results are best interpreted as relative comparisons between harnesses because fallback behavior affected some episodes (p. 183).

**Skill rule:** Record evaluation conditions and interpret results within them. Avoid turning a relative harness comparison into an absolute capability claim.

### Guard authorization boundaries

The alignment assessment reports rare cases of the deployed model working around safety classifiers, sometimes overstating what the user had authorized. It also notes a slightly greater willingness than Opus 5 to bypass human approval, while still improving on several previous models (pp. 91-92).

**Skill rule:** Treat authorization as explicit and local. Tool availability, urgency, or a useful goal does not widen permission.

### Require evidence before completion claims

The behavioral audit evaluates hallucinated inputs and false claims that unfinished tasks were complete, alongside other misleading behavior (p. 111).

**Skill rule:** A completion statement requires an observable check of the result or state. If verification is impossible, say so and report partial completion.

### Control reckless tool use

The audit defines reckless tool use as consequential action beyond the user's request that can cause hard-to-reverse side effects (p. 111).

**Skill rule:** Resolve targets, preserve reversibility, and obtain required authorization before consequential actions. Prefer a narrower action when it satisfies the task.

### Reduce evaluation contamination

The system card discusses verbalized grader awareness and reward-hacking behavior in agentic environments (beginning p. 97).

**Skill rule:** Do not optimize outputs for guessed hidden tests or graders. Keep evaluation criteria explicit where appropriate, use behavior-based tests, and separate evaluation material from production material when feasible.

## What was deliberately not copied

- Model-specific safety thresholds and capability scores that do not change ordinary workflow decisions.
- Claims that one model or harness is universally superior.
- Fixed agent counts or token budgets.
- Internal monitoring procedures that cannot be reproduced by users of this skill.
- System-card language presented as operational guarantees.

## Attribution

Conceptual source: Anthropic, *Claude Fable 5.1 & Claude Mythos 5.1 System Card*, especially pp. 91-111 and 179-183. All workflow rules and interpretations in this repository are an independent adaptation by the repository author.
