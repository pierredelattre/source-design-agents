# Agent prompt conventions

## Structure of an agent definition

Every agent lives in `agents/<agent-name>/` and contains:

```
agents/agent-name/
├── instructions.md      # System prompt — behaviour, goals, rules
├── tools/               # Custom tools this agent can call (optional)
├── files/               # Local reference files (optional)
├── agent.config.json    # Model, params, wiring (optional)
└── examples/            # Sample inputs and expected outputs
```

## instructions.md template

```markdown
# Agent: <Name>

## Role
One sentence. What this agent does and for whom.

## Inputs
- `input_name` (type): description

## Outputs
- `output_name` (format: MD | JSON | CSpec YAML): description

## Rules
- [Tool constraints: which tools to use and which to avoid]
- [Format rules: see docs/design/conventions.md]
- [Exchange format: CSpec YAML for any Figma content]

## Steps
1. ...
2. ...
```

## Output format rules (apply to all agents)

- Docs and text: Markdown, no em-dashes, no filler phrases, minimum viable length.
- Figma content: CSpec YAML (Bridge format). Never raw JSON or Markdown fragments.
- Structured data: JSON with a defined schema documented in the agent's README.

## Tool assignment

| Task | Tool |
|------|------|
| Create Figma frames / components | Bridge (`/design-workflow`) |
| Inspect, lint, audit Figma | figma-cli (`fig-start`) |
| Export tokens | `figma-cli tokens` or `figma-cli var list` |
| Export Storybook stories | `figma-cli export storybook` |
| Screenshot for validation | `figma-cli verify "NODE_ID"` |

## Agent index

The canonical list of agents (role, status, inputs, outputs, tools) is in `docs/agents.md`. Read it before creating or modifying any agent.

## Memory model

Agents have no hidden state between sessions. Persistent knowledge lives in:

- `docs/decisions/` — architectural and DS decisions
- `docs/design/` — UI/UX and DS rules
- `docs/architecture/` — stack and integration decisions
- `docs/workflows/` — process playbooks
- `docs/prompts/` — this file and agent definitions
- `docs/resources/` — design knowledge base (synthesised from `/pdfs/`)

Agents must read the relevant files in `docs/` before proposing designs, architectures, naming schemes, or workflows.

## Knowledge base usage (mandatory for DS/UX work)

For any task involving design systems, UX, accessibility, research, or copy:

1. Read the relevant `docs/resources/` file before responding:
   - DS questions: `docs/resources/design-systems.md`
   - UX/UI questions: `docs/resources/ux-ui-reference.md`
   - Routing: `docs/resources/knowledge-index.md`
2. Cite principles from `docs/resources/` rather than inventing new ones from scratch.
3. If a principle is adopted for the project, record it in `docs/decisions/` and note it in `CHANGELOG.md`.
4. Do not paste raw `/pdfs/` content into prompts. Summarise and reference.
5. Confirm with the user before: adding new thematic categories, removing resources, or changing how an agent uses the knowledge base.
