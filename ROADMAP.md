# Roadmap

## Long-term goal

Make Cursor a first-class Kit client: anything a team does in Kit's web app (hire, triage security reports, run outreach, train, review) can be done from the editor after one install, while the plugin stays a thin manifest.

Kit's MCP server is the single source of truth. Tools, prompts and skills ship from `startupkit.app`, so every client (Cursor, Claude Code, Codex) gets the same behavior on the same day and this repo rarely needs a release.

## Principles

- **Server first.** New capability lands as an MCP tool, prompt or `skill://` resource in Kit, not as plugin files.
- **Least privilege.** OAuth scopes per module, writes off by default, irreversible write tools ask before they act.
- **Minimal surface.** Add a plugin component only when MCP cannot express it: rules scoped to files, hooks, Cursor-specific commands.

## Milestones

1. **v0.1: connect.** Remote MCP with OAuth. Listed in the Cursor Marketplace.
2. **v0.2: discoverability.** Cursor section on Kit's "Connecting AI assistants" docs page and the MCP Setup screen; install badge on startupkit.app.
3. **v0.3: engineering workflows.** Where Kit meets the codebase: triage a CSIRT report against the open repo, review a code-assignment submission, turn a report into a fix PR.
4. **v1.0: parity.** Every Kit module reachable from Cursor, with prompts for its core workflows, tracked against the tool list the server publishes.
