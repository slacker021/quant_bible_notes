# General Git Message Template for Commits
Below is the standard Git message commit template that is to be used for every single commit made, effective as of the time of this markdown document being created: 
```text
<type>(<scope>): <subject line/title under 100 characters>

- Rationale: The theoretical, formal, or visual motivation for the revision.
- Mechanics: The precise modification made (e.g., altered definition, refactored proof, updated frontmatter).
- Coherence: Impact on downstream notes, Mathlib alignment, or garden rendering.

[Footer: Optional metadata, backlinks, and formal citations]
Refs: [[Volume/Module#Target]] | Paper / Lemma Identifier
Lean-Audit: Pass (Mathlib canonical / zero sorry)
Publish-Status: Public / Private / Frontmatter updated
```
---
# Template Specifications/Rules

### Header Types and Semantics
The header `<type>(<scope>): <subject>` has three components: 
1. `<type>` has the following potential field categories that can be entered:
  - `note:` Adding, updating, expanding, or pruning Markdown expository prose, explanations, and pedagogical text.
  - `def`: Introducing or altering a formal mathematical definition, axiom, or foundational assumption.
  - `proof`: Adding, modifying, or completing derivations in Markdown or formal proofs within the Lean 4 repository.
  - `garden`: Alterations to the Digital Garden configuration, navigation, frontmatter flags, visual settings, or note publishing toggles.
  - `refactor`: Reorganizing folder hierarchies, splitting notes, standardizing backlinks, or moving modules without altering core content.
  - `fix`: Correcting mathematical errors, grammatical slips, dead Obsidian links, or broken Lean tactics.

2. `(<scope>)` identifies the precise volume, module, or component being addressed directly.
3. `<subject line/title under 72 characters>` is a concise explanation of what the commit is all about

### Body
Git line diffs already capture character deletions and insertions, as well as file additions, removals, and modifications. Thus, the commit message body is focused on explaining why 
the alteration was even made in the first place: 
- Rationale: Explains the conceptual motivation. Was an assumption overly restrictive? Did a paragraph obscure the underlying measure-theoretic mechanics? 
  Was a Lean 4 proof refactored to align with updated Mathlib conventions?
- Mechanics: Details the exact nature of the change—such as modifying a premise in a theorem statement, eliminating informal heuristics, or adjusting a Digital Garden YAML property.
- Coherence: Notes the structural reverberations across the digital garden, such as broken backlinks, updated cross-references, or changes to the publish graph.

### Footer
The footer maintains traceability in the form of custom metadata: 
- Refs: Internal wikilinks ([[Note Name]]) or canonical literature citations (author, theorem number, DOI) that ground the modification.
- Formal / Verification Status: Verification tags for the Lean 4 repository (e.g., confirming #print axioms displays standard classical foundations with no sorryAx).
- Publish Status: Flags indicating note publication state (publish: true), frontmatter alterations, or metadata synchronization.

---
# General Conventions
- The use of grammatical contractions is (e.g. isn't, ain't, aren't, don't) are strictly prohibited.
- The use of emojis is strictly prohibited.
- All messages are to be typed in gender-neutral and third-person prose for uniformity, consistency, and impersonality.
