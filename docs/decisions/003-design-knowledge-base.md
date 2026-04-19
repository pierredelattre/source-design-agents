# 003 — Design Knowledge Base

**Status:** Accepted
**Date:** 2026-04-19

## Context

The `/pdfs/` directory contains a curated set of design books and guides covering design systems, UX/UI methodology, and organisational practice. Before this decision, there was no formal convention for how agents or collaborators should reference this material.

## Decision

We treat `/pdfs/` as the project's official design knowledge base. The canonical interface to this knowledge base is `docs/resources/`, not the raw files.

Specifically:
- `docs/resources/knowledge-index.md` is the master index of all resources — theme, best-use bullets, and target roles/agents.
- `docs/resources/design-systems.md` synthesises principles from the five DS-focused books.
- `docs/resources/ux-ui-reference.md` synthesises UX/UI concepts from the broad reference EPUB.

## Rationale

Reading raw PDFs/EPUBs in every prompt is expensive and unreliable. The `docs/resources/` synthesis files provide stable, curated summaries that agents and collaborators can reference efficiently. The raw files remain the authoritative source for deep dives when a specific passage is needed.

## Consequences

**Positive:**
- Agents have a consistent, low-token reference for design principles.
- Principles are grounded in established literature, not invented ad hoc.
- New team members can onboard to the project's design thinking via `docs/resources/`.

**Negative:**
- The synthesis files are frozen at the time of writing and must be updated manually if the PDF set changes.
- Synthesis always involves some loss of nuance; agents must read the raw source for deep-dive work.

## Conventions for using this knowledge base

1. **Reference, do not copy.** Agents and prompts cite principles from `docs/resources/*.md`. They do not paste raw book content into prompts.
2. **Summarise for context.** When referencing a principle, state it in one sentence and note the source (e.g., "Kholmatova distinguishes functional from perceptual patterns").
3. **Update on adoption.** When the project adopts a new principle from this knowledge base, record it in the relevant `docs/` file and note it in `CHANGELOG.md`.
4. **Add new resources carefully.** New PDFs/EPUBs added to `/pdfs/` require a corresponding entry in `knowledge-index.md` and, if significant, a new or updated sub-file. Record the addition in this decision record or create a new one.
5. **Confirm before removing.** Removing or deprecating a resource requires user confirmation and a note in this record.
