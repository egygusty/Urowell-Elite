# Urowell-Elite Inter-Agent Memory

This directory is dedicated to maintaining context, history, and seamless handoffs between autonomous agents working on the `Urowell-Elite` repository. Specifically, this bridges the gap between **Manus** (cloud-based autonomous agent) and **Antigravity** (local VS Code agent).

## Directory Structure

*   **`/context/`**: Persistent project context.
    *   `project-rules.md`: Core directives, tech stack, and coding standards.
    *   `architecture.md`: Current architecture, integrations, and file structure.
*   **`/handoffs/`**: Communication between agents.
    *   `latest-handoff.md`: The single source of truth for the most recent state. When an agent finishes a session, it updates this file for the next agent.
*   **`/logs/`**: Historical record of major changes (optional, but good for tracking).

## Handoff Protocol

When **Manus** or **Antigravity** completes a session:
1.  Update `.agent-memory/handoffs/latest-handoff.md` with what was done, what is pending, and any newly discovered constraints.
2.  Commit the changes to the repository.
3.  Push to the remote repository.

When **Manus** or **Antigravity** begins a session:
1.  Pull the latest changes from the remote repository.
2.  Read `.agent-memory/handoffs/latest-handoff.md` to understand the current state.
3.  Read `.agent-memory/context/project-rules.md` to ensure compliance with project standards.
