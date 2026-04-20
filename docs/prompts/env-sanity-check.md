# Env sanity check — prompt

Paste this into chat to verify the environment for Figma / Bridge / DS agents.

```txt
Use your "Env sanity check behaviour" as defined in CLAUDE.md.

Goal:
Check whether the current environment is ready for Figma / Bridge / design-system
agents, and tell me exactly what I still need to do manually.

Scope:
- figma-cli installation and `figma-cli connect`
- `/design-workflow setup` reminder for the active Figma file
- `TOKEN_OUTPUT_PATH`, `STORYBOOK_STORIES_PATH`, `DOCS_OUTPUT_PATH`
  presence in the relevant agent.config.json files

Constraints:
- Do NOT assume commands have been run if you cannot confirm.
- Do NOT guess secrets or absolute paths.
- Produce:
  - A checklist of items that look OK
  - A checklist of items I must configure or run,
    with explicit instructions (run this command / edit that file)
```
