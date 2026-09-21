# Kit for Cursor

Cursor plugin for [Kit](https://startupkit.app). It adds Kit's MCP server, so the agent in Cursor can read and act on your hiring pipeline, security reports, outreach campaigns, training programs and review cycles.

- **Hiring**: list job postings and applications, summarize a candidate, advance or reject an application, save notes, stage replies to candidates as drafts
- **Security (CSIRT)**: triage a report, check it for duplicates, suggest severity, propose and approve bounties
- **Outreach**: manage campaigns and prospects, draft emails, approve pending messages
- **Compensation Research**: salary benchmarks, role comparisons, market trends (read-only)
- **Training, Performance, Team**: programs and completion status, review cycles, members and invitations
- **Docs**: search Kit's documentation and plans

Free-form replies to candidates and researchers are saved as drafts for a teammate to send from Kit. Tools that do email someone, such as interview invitations, clarification requests and deadline extensions, are annotated as destructive, so clients that honor MCP hints ask before running them.

## Install

In Cursor, open the plugin marketplace, search for **Kit** and click **Install**.

The plugin adds one MCP server, `kit`, at `https://startupkit.app/api/v1/mcp` (streamable HTTP). If you already added a server named `kit` by hand, remove it so each tool shows up once.

Without the marketplace, [add the server with one click](https://cursor.com/install-mcp?name=kit&config=eyJ1cmwiOiJodHRwczovL3N0YXJ0dXBraXQuYXBwL2FwaS92MS9tY3AifQ%3D%3D), or put this in `.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "kit": { "url": "https://startupkit.app/api/v1/mcp" }
  }
}
```

## Sign in and permissions

The first `kit` tool call opens Kit's consent screen in your browser. There is no API key to paste: the server uses OAuth with dynamic client registration. Pick an account, then choose **Read** or **Read & write** for each module: Hiring, CSIRT, Outreach, Training, Performance, Team. Compensation Research is read-only. Writes are off by default. Modules outside your role can't be granted, and tools from modules you didn't grant never reach the agent.

Revoke a connection under [Settings → Connected clients](https://startupkit.app/user/connected_clients).

## Try it

- "Which applications for the Senior Rails Engineer role are waiting on me?"
- "Summarize this candidate and save a note for the hiring manager."
- "Triage the newest security report and check it for duplicates."
- "What's the median salary for a senior backend engineer in Warsaw?"

Kit's server also ships MCP prompts (`hiring_summarize_candidate`, `csirt_triage_report`, `outreach_draft_followup` and others) and `skill://` resources. They update on the server; the plugin needs no release for them.

## Docs

- [Connecting AI assistants](https://startupkit.app/docs/connecting-ai-assistants)
- [Agent setup prompt](https://startupkit.app/agent-setup/prompt.md)
- [Roadmap](ROADMAP.md)

## Development

```bash
node scripts/validate.mjs
```

## License

[MIT](LICENSE)
