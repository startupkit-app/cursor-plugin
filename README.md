# Kit for Cursor

Official Cursor plugin for [Kit](https://startupkit.app). It connects Cursor to Kit's MCP server, so the agent can work with your hiring pipeline, security reports, outreach campaigns, training programs and salary data without leaving the editor.

- **Hiring**: list job postings and applications, summarize candidates, advance stages, message candidates
- **Security (CSIRT)**: triage vulnerability reports, check duplicates, propose bounties
- **Outreach**: manage campaigns and prospects, draft and approve emails
- **Compensation research**: salary benchmarks, role comparisons, market trends
- **Training, performance and team**: training programs and completion status, review cycles, members and invitations
- **Docs**: search Kit's documentation and plans

## Install

In Cursor, open the plugin marketplace, search for **Kit** and click **Install**.

The plugin adds one MCP server, `kit`, at `https://startupkit.app/api/v1/mcp`. If you already added a server named `kit` by hand, remove it to avoid duplicate tools.

Without the marketplace, [add the server with one click](https://cursor.com/install-mcp?name=kit&config=eyJ1cmwiOiJodHRwczovL3N0YXJ0dXBraXQuYXBwL2FwaS92MS9tY3AifQ%3D%3D), or put this in `.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "kit": { "url": "https://startupkit.app/api/v1/mcp" }
  }
}
```

## Sign in and permissions

The first `kit` tool call opens Kit's consent screen in your browser. Pick the account, then choose **Read** or **Read & write** per module (Hiring, CSIRT, Outreach, Training, Performance, Team; Compensation Research is read-only). Writes are off by default, and modules outside your role can't be granted. Tools from modules you didn't grant never reach the agent.

Review or revoke connections under [Account Settings → Connected clients](https://startupkit.app/user/connected_clients).

## Try it

- "Which applications for the Senior Rails Engineer role are waiting on me?"
- "Summarize this candidate and draft a note for the hiring manager."
- "Triage the newest security report and check it for duplicates."
- "What's the salary benchmark for a staff engineer in Berlin?"

Kit's server also ships MCP prompts (`hiring_summarize_candidate`, `csirt_triage_report`, `outreach_draft_followup` and more) and `skill://` resources, so workflows live on the server and stay current without plugin updates.

## Docs

- [Connecting AI assistants](https://startupkit.app/docs/connecting-ai-assistants)
- [Agent setup prompt](https://startupkit.app/agent-setup/prompt.md)
- [Roadmap](ROADMAP.md)

## Development

```bash
node scripts/validate-template.mjs
```

## License

[MIT](LICENSE)
