# Workflow — Bridge fix loop and decision logging

Describes the convention for triggering `agent-design-decision-logger` after an accepted Bridge fix, so every DS-level correction becomes a durable decision record.

## When to trigger the logger

Trigger `agent-design-decision-logger` after a Bridge fix session when **all three conditions** are true:

1. A Figma correction was accepted (not just previewed or discarded).
2. The correction changes a DS rule, token usage, or component behaviour — not just the content of one screen.
3. The same rule would apply to future work (i.e. it is not a one-off layout exception).

**Do NOT log:**
- Content changes (copy, image swaps, colour tweaks that do not affect tokens).
- One-off exceptions that should not propagate to other components.
- Corrections that reverse a previous fix without a new rationale.

## What to pass as input

Give the agent a plain-text diff block plus three pieces of context:

```
Component: [component name]
Correction: [what changed — old value → new value]
Scope: global | local
Reason: [why the change was made]
```

Example:

```
Component: Button/Primary
Correction: border-radius changed from hardcoded 4px to $radius/md
Scope: global
Reason: hardcoded values were flagged by DS lint; all Button variants must use the radius token
```

If the Bridge fix session produced a structured diff automatically, paste it in full. The agent will extract what it needs.

## What the agent produces

1. A draft ADR file at `docs/decisions/NNN-title.md` following the template in `docs/decisions/README.md`.
2. A short list of files to update (conventions doc, changelog, affected agent instructions).

You review the draft, edit if needed, and save it. The agent does not write files autonomously unless you ask it to.

## Step-by-step (manual convention)

Until Bridge's fix loop is automated, follow these steps after each qualifying fix:

1. Copy the fix diff and context (component, correction, scope, reason).
2. Open a new Claude Code session with `agent-design-decision-logger`.
3. Paste the input using the format above.
4. Review the ADR draft.
5. Save the ADR to `docs/decisions/NNN-title.md`.
6. Apply the file updates listed by the agent (`docs/design/`, `CHANGELOG.md`, etc.).
7. Update the index table in `docs/decisions/README.md`.

## Prompt snippet (copy-paste)

Use this right after a Bridge fix is accepted and should become a DS-level rule.

```txt
Use the agent-design-decision-logger.

Context:
Component: [name]
Correction: [old -> new]
Scope: global
Reason: [why]

Goal:
Draft a Design System Decision Record for `docs/decisions/`,
including:
- Context
- Decision
- Rationale
- Consequences
- Status (Proposed or Accepted)
- List of related files to update (if any)
```

## Automation path (future)

When Bridge exposes a post-fix hook, wire it to call `agent-design-decision-logger` automatically with the structured diff. The `agent.config.json` for the logger includes a `bridge.hook_trigger: "bridge-fix-diff"` placeholder for this integration.

See `agents/agent-design-decision-logger/agent.config.json` for the wiring spec.

## Scope classification guide

| Scope | Meaning | Log as |
|-------|---------|--------|
| global | Rule applies to all instances of this component or token across the DS | ADR in `docs/decisions/` |
| local | One-off exception for a specific screen or context | Note in `CHANGELOG.md` only |

When in doubt, classify as global and let the ADR review catch any over-logging.
