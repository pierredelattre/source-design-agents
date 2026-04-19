# Agents

This folder contains all project agents.

Each agent lives in its own subfolder:

- One agent per directory
- Clear separation between configuration, instructions and tools

## Agent folder structure

For each agent, use the following structure:

agent-name/
- instructions.md  — system prompt, behaviour, goals
- tools/           — custom tools the agent can call
- files/           — local reference files for this agent (optional)
- agent.json or agent.config.(ts|js|yaml) — wiring, model, params (optional)

Example:

product-designer-assistant/
- instructions.md
- tools/
- files/
- agent.config.json

For any work involving agents, first read `agents/README.md` and
the specific `instructions.md` for the agent you are modifying
or creating.
