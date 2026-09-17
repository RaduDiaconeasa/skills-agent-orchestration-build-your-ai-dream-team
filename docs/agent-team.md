# Agent team for Mona's Project Pulse dashboard

I will use a four-agent custom team orchestrated through GitHub Copilot CLI in a Codespace to build Mona's Project Pulse dashboard.

- Orchestrator — Model: Claude Opus 4.7 (copilot). Responsibility: coordinates the full workflow, breaks the work into phases, delegates to specialist agents, and verifies integration. Definition: `.github/agents/orchestrator.agent.md`.
- Planner — Model: Claude Opus 4.7 (copilot). Responsibility: researches the repository, reads relevant files, identifies constraints and edge cases, and produces a practical implementation plan with file assignments and dependency sequencing. Definition: `.github/agents/planner.agent.md`.
- Designer — Model: Gemini 3.1 Pro (copilot). Responsibility: shapes the dashboard UX, information hierarchy, visual polish, accessibility, and interaction design for the Project Pulse experience. Definition: `.github/agents/designer.agent.md`.
- Coder — Model: GPT-5.5 (copilot). Responsibility: implements the code, fixes bugs, wires up logic, and validates behavior within the scoped files assigned by the Orchestrator. Definition: `.github/agents/coder.agent.md`.

This team lives under the repository's agent folder (`.github/agents/`), and the orchestration flow runs through GitHub Copilot CLI in the Codespace so the agents can collaborate on the dashboard build while keeping responsibilities clearly separated.
