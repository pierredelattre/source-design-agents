# Playbook — Product Designer

Covers the full product design cycle. Each step maps to one or more agents.

## 1. Problem framing

**Agent:** `agent-problem-framing`
**Input:** Raw product brief (text)
**Output:** Problem statement, assumptions, risks, success metrics (Markdown)

Steps:
1. Paste or describe the brief.
2. Agent generates a structured problem frame (JTBD, constraints, KPIs).
3. Review and adjust before moving to research.

## 2. Research synthesis

**Agent:** `agent-ux-research-synthesizer`
**Input:** Interview notes, analytics exports, survey results (text / MD)
**Output:** Top insights, personas, empathy map, jobs-to-be-done

## 3. User flows and IA

**Agent:** `agent-flow-builder`
**Input:** User stories or backlog items
**Output:** Mermaid flow diagrams, screen checklists, edge-case coverage map

Validation: `agent-flow-qa` checks for missing states, error paths, and empty states.

## 4. Wireframes

**Tool:** Bridge (`/design-workflow`)
**Input:** Screen description + DS context (from Bridge setup)
**Output:** Lo-fi frames in Figma using DS components

Agent assist: `agent-wireframe-to-ds` proposes the best DS component combination for a given screen. Exchange format: CSpec YAML.

## 5. UI design

**Tool:** Bridge for creation, figma-cli for verification
**Agents:** `agent-component-finder`, `agent-variant-builder`

After each creation: `figma-cli verify "NODE_ID"` for screenshot validation.

## 6. Accessibility audit

**Agent:** `agent-a11y-audit`
**Tool:** `fig-start a11y audit` (do not reimplement — call the CLI)
**Output:** Contrast failures, touch target issues, focus order problems

## 7. Handoff

**Agent:** `agent-storybook-linker` maps Figma components to Storybook stories.
**Agent:** `agent-doc-writer` generates functional specs and DS docs from maquettes.

## 8. Measurement and iteration

**Agent:** `agent-design-decision-logger` hooks into Bridge's fix workflow: every Figma correction becomes a logged decision in `docs/decisions/`.
**Agent:** `agent-experiment-designer` proposes A/B tests and iteration plans.
