# Stop Writing Bigger Prompts

Your agent does not need another 4,000-word persona.

It needs a workflow that can survive contact with evidence.

**Fable Forensic Skill** turns research, implementation, review, and repair into an auditable process: define the scope, inspect the evidence, delegate bounded work, verify the actual deliverable, record failures, repair defects, and report only what can be supported.

Yes, this repository uses the dramatic headline on purpose.

No, it is not a magic prompt.

It is quality assurance wearing an influencer's coat.

## What makes this different

This skill translates page-level system card findings into practical workflow controls for evidence, delegation, authorization, and completion verification.

The distinction is not a Fable persona, a larger prompt, or a claim that one model is “best.” The repository shows how specific evaluation findings become operational rules, with page-level attribution and explicit limits on what can be concluded.

**Do not evaluate this project from the landing page alone.** Read the actual [SKILL.md](SKILL.md), then inspect the [system-card-derived design notes](references/system-card-derived-design.md).

The skill's activation boundary is defined directly in its frontmatter:

> Audit, fact-check, and verify research, implementations, repairs, and output files with explicit scope, bounded delegation, failure logging, and human-auditable delivery. Use when asked to “verify this actually works,” “check the output file,” “confirm it really finished,” investigate silent omissions or false completion, or review permission drift; skip trivial requests that need no investigation or validation.

## What it does

- Establishes an explicit task and authorization boundary
- Separates observed facts from inference
- Delegates only bounded, independently useful work
- Gives subagents scoped context instead of the entire conversation
- Preserves material failure paths instead of hiding them
- Verifies the final artifact rather than trusting the execution trace
- Blocks unsupported completion claims
- Measures quality, latency, token use, and cost when comparison matters
- Produces a result a human can audit without reading every internal step

## The workflow

```text
Research
  -> Decompose
  -> Execute
  -> Verify
  -> Record failures
  -> Repair
  -> Re-verify
  -> Deliver auditable evidence
```

This is an adaptation of the Black Pug method: investigation, production, verification, failure, and repair are treated as one reusable operating process rather than disconnected prompts.

## Why “Fable”?

The skill incorporates conservative workflow lessons derived from the *Claude Fable 5.1 & Claude Mythos 5.1 System Card*, including:

- grading the final deliverable separately from intermediate agent output;
- dynamically assigning asynchronous subagents;
- giving subagents bounded instructions rather than the entire original task;
- tracking agent lifecycle and total resource use;
- comparing quality, latency, tokens, and cost;
- preventing permission drift, reckless tool use, and false completion claims; and
- reducing contamination from guessed graders or hidden tests.

See [the design notes](references/system-card-derived-design.md) for page-level attribution, limits, and the exact translation from evaluation finding to workflow control.

This project is independent and unofficial. It is not affiliated with or endorsed by Anthropic.

## Install

Place this repository in the skills directory supported by your agent environment, preserving the repository structure. For environments that use a per-skill directory, the result should resemble:

```text
skills/
└── fable-forensic-skill/
    ├── SKILL.md
    ├── agents/
    │   └── openai.yaml
    └── references/
        ├── system-card-derived-design.md
        └── verification-checklist.md
```

Restart or refresh the environment if it caches skill metadata.

## Use

Invoke the skill explicitly when supported:

```text
Use $fable-forensic-skill to investigate this failure, implement the repair,
verify the final behavior, and report the evidence and remaining uncertainty.
```

Automatic discovery may also select it for complex tasks where evidence, permission boundaries, or verification materially affect correctness.

## Operating depths

- **Light:** Low consequence and directly verifiable.
- **Standard:** Material consequence or multi-stage verification.
- **High assurance:** High consequence or difficult reversibility; apply the full [verification checklist](references/verification-checklist.md).

Consequence takes precedence over verification simplicity. A production action does not become Light merely because one command or one check can complete it. A user may request a deeper mode, but cannot use a depth label to lower the required minimum. The skill intentionally avoids turning every small request into an investigation while preserving a hard floor for consequential work.

## What this is not

- A jailbreak
- A hidden system prompt
- A claim that multi-agent systems are always better
- A replacement for human authorization
- A guarantee that a model will never fail
- An excuse to bury the user under execution logs

## License

MIT. See [LICENSE](LICENSE).

## Revision history

See [CHANGELOG.md](CHANGELOG.md) for the public record of material changes and their rationale.
