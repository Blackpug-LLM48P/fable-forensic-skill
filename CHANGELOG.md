# Changelog

All material changes to the public skill are recorded here. This project uses semantic versioning for releases when practical.

## [Unreleased]

### Changed — 2026-10-16

- Corrected the unpublished article's Zenn rendering: use a single-line rights comment, render the rights label as bold text, and expose all eight primary references as direct links.
- Expanded the unpublished Japanese theory article to v0.2, approximately 15,000 non-whitespace characters, with worked examples, probability and decoding distinctions, audit states, evidence handling, and an evaluation plan.
- Added primary references on decoding, local typicality, detector robustness, and language-related detector bias; distinguished proposed designs from measured results.
- Retained `published: false` and the article-specific rights reservation; the forensic prompt and private evaluation materials remain excluded.

### Added — 2026-10-16

- Added a new Japanese Zenn theory draft, `articles/ai-forensics-relation-level-methodology.md`, with `published: false`.
- Documented relation-level evidence, auditable deferral, affirmative function findings, and mixed support within a finding, with synthetic examples and primary references.
- Added a file-specific All rights reserved notice for this new article and clarified the default MIT scope without changing permissions already granted for earlier materials.


### Changed

- Moved the repository's primary differentiator near the top of the README: page-level system card findings are translated into practical workflow controls.
- Added direct links to `SKILL.md` and the system-card-derived design notes so reviewers can inspect the implementation rather than infer it from promotional copy.
- Exposed the complete skill activation description in the README, including the boundary that prevents trivial requests from triggering a forensic workflow.
- Avoided an unsupported “first” claim because no exhaustive survey of all Fable-related skills was performed.
- Added user-facing discovery phrases such as “verify this actually works,” “check the output file,” and “confirm it really finished” to the skill description.
- Added explicit `depth: light`, `depth: standard`, and `depth: high-assurance` overrides, conservative defaults, and observable escalation conditions.
- Required the lead agent to treat subagent reports as unverified claims and independently inspect decisive evidence, artifacts, and state.
- Clarified that Light mode narrows evidence and test breadth but does not waive authorization, direct verification, or truthful completion gates.
- Replaced the ambiguous depth-selection prose with a deterministic consequence-by-verification model and an explicit precedence order.
- Defined consequence as the minimum depth floor: a simple verification path cannot downgrade high-consequence work, and a user-supplied depth label may raise but not lower that floor.
- Added delegation, conflicting evidence, failed verification, scope expansion, and reduced reversibility as observable escalation triggers.

## [1.0.0] - 2026-09-02

### Added

- Initial English-language release of the Fable Forensic Skill.
- Evidence-driven workflow covering task scope, evidence inventory, bounded delegation, execution controls, deliverable isolation, verification, failure logging, repair, and completion gates.
- Light, Standard, and High-assurance operating depths.
- System-card-derived design notes with page-level attribution to the *Claude Fable 5.1 & Claude Mythos 5.1 System Card*.
- High-assurance verification checklist.
- Agent UI metadata and MIT license.
