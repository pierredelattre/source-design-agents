# 005 — Design decision logging via agent-design-decision-logger

**Status:** Accepted
**Date:** 2026-04-20

## Context

Bridge's fix workflow produces corrections to Figma components and token usage. Without a logging step, these corrections exist only in Figma and in the git diff — they are not discoverable as rules for future work. Over time, the DS accumulates invisible conventions that new contributors (human or agent) have no way to find.

The same problem affected architecture decisions before ADRs were introduced. The fix is the same: make every significant decision a first-class, searchable document.

## Decision

After each accepted Bridge fix that changes a DS rule or token convention, the diff and context are fed to `agent-design-decision-logger`, which produces a draft ADR in `docs/decisions/`. The human reviews and saves it. One-off local exceptions are logged in `CHANGELOG.md` only — not as ADRs.

The full protocol is documented in `docs/workflows/bridge-fix-loop.md`.

## Rationale

- ADRs in `docs/decisions/` are already the authoritative source for DS and architecture decisions. Reusing this format means no new conventions to learn.
- Agents read `docs/decisions/` at the start of every session — logged fixes automatically become part of the agent's working context.
- The logger agent is triggered manually for now. A post-fix hook can automate it later without changing the protocol.

## Consequences

- Every qualifying Bridge fix produces a new or updated ADR.
- `docs/decisions/README.md` index must be updated after each new ADR.
- Agents that work on the affected component must re-read `docs/decisions/` to pick up the new rule.
- One-off exceptions that do not produce ADRs must still appear in `CHANGELOG.md` so they are not lost.

## Alternatives considered

- **Log to CHANGELOG.md only**: loses the structured context (rationale, alternatives, consequences) that makes decisions reusable.
- **Embed rules directly in instructions.md**: creates duplication and makes it hard to track when a rule was introduced and why.
