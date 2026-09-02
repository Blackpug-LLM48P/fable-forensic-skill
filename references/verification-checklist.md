# High-assurance verification checklist

Use this checklist for consequential, published, destructive, expensive, or difficult-to-reverse work. Apply only the items relevant to the task.

## Contract

- The requested outcome and deliverable are explicit.
- Constraints, exclusions, and acceptance criteria are recorded.
- The authorization boundary is no broader than the user's request.
- Assumptions that could change the result are confirmed or disclosed.

## Evidence

- Decisive claims are tied to inspected evidence.
- Primary sources are preferred where available.
- Current facts have been checked against current sources.
- Inferences are labeled and do not masquerade as observations.
- Missing, inaccessible, or uninspected material is identified.

## Delegation

- Every delegated task is independent and bounded.
- Each instruction packet contains only relevant context.
- Subagent findings include evidence, uncertainty, and return status.
- Conflicting findings are resolved by the lead rather than silently averaged.
- Redundant or stalled work is stopped.

## Execution safety

- Exact mutation targets were resolved before action.
- Unrelated user work was preserved.
- Hard-to-reverse actions had explicit authority.
- Failure paths and method changes were recorded.
- Any expansion of scope was approved rather than inferred.

## Deliverable verification

- The final artifact was opened, rendered, executed, or otherwise inspected directly.
- Functional tests check observable behavior rather than wording alone.
- Important counts, formulas, links, citations, and file paths were checked.
- Negative and boundary cases were tested when relevant.
- The final deliverable is independent of intermediate tool output.

## Completion report

- The reported outcome matches the verified state.
- Partial work is labeled partial.
- Known defects, uncertainties, and untested areas are visible.
- The user can understand the result without reading the execution trace.
- Quality, latency, resource use, and cost are reported when the comparison needs them.
