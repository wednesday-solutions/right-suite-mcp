<p align="center"><img src="logo.png" width="96" alt="Right Suite logo"></p>

# Right Suite: test your go-to-market on 100+ simulated buyers, from Claude, ChatGPT and any AI assistant

Find out if buyers will pay before you spend weeks or ad money finding out. Paste your price,
landing page, cold email, ad or competitor list into the chat, and Right Suite runs it past 100+
simulated buyers modelled on your audience. In about 10 to 20 minutes you get a verdict, the
objections that came up most, and the changes to make.

Built for founders, marketers and agencies who want an answer before launch day: price testing,
landing page feedback, cold email testing, ad testing and positioning research in one MCP server.

**Website:** https://www.rightsuite.co/mcp?utm_source=github_repo&utm_medium=directory&utm_campaign=mcp_listings

**Server URL:** `https://www.rightsuite.co/api/mcp` (Streamable HTTP, OAuth: sign in with your Right Suite account)

## Install

| Where | How |
|---|---|
| Claude (Claude.ai, Claude Desktop) | Settings → Connectors → **Add custom connector**, paste `https://www.rightsuite.co/api/mcp` |
| ChatGPT | Settings → Apps & Connectors → **Create**, paste `https://www.rightsuite.co/api/mcp` |
| Claude Code | `claude mcp add --transport http right-suite https://www.rightsuite.co/api/mcp` |
| Cursor | See below |
| Any MCP client | Point it at `https://www.rightsuite.co/api/mcp` (Streamable HTTP) |

## What you can do

- **Price:** would buyers pay this, and what range fits.
- **Landing page and marketing copy:** where readers get lost, what they don't believe, whether they keep reading.
- **Cold email and DMs:** open, reply, ignore or delete, with line-level fixes.
- **Ads:** stop the scroll and click, or scroll past, with fixes to the hook, copy and CTA.
- **Audience:** rank 2 to 4 segments by purchase intent, urgency and willingness to pay.
- **Positioning:** put your offer next to 1 to 3 competitors and see who buyers pick and why.
- **Channel:** rank 2 to 8 channels by where your buyers actually pay attention.

Every run also lands on your Right Suite dashboard.

## Connect

### Claude (Claude.ai, Claude Desktop)
Settings → Connectors → **Add custom connector**. Name it Right Suite, paste
`https://www.rightsuite.co/api/mcp`, click **Add**, then **Connect** and sign in with your Right
Suite account.

### ChatGPT
Settings → Apps & Connectors → **Create** (developer mode), paste `https://www.rightsuite.co/api/mcp`,
choose OAuth, and sign in with your Right Suite account.

### Claude Code
```bash
claude mcp add --transport http right-suite https://www.rightsuite.co/api/mcp
```
Then run `/mcp` to sign in. Or install this repo as a plugin to get the server and the
`right-suite` skill together.

### Cursor
Add to `~/.cursor/mcp.json`:
```json
{
  "mcpServers": {
    "right-suite": { "url": "https://www.rightsuite.co/api/mcp" }
  }
}
```

### VS Code
Add to `.vscode/mcp.json`:
```json
{
  "servers": {
    "right-suite": { "type": "http", "url": "https://www.rightsuite.co/api/mcp" }
  }
}
```

### Kiro
[![Add to Kiro](https://kiro.dev/images/add-to-kiro.svg)](https://kiro.dev/launch/mcp/add?name=right-suite&config=%7B%22url%22%3A%22https%3A%2F%2Fwww.rightsuite.co%2Fapi%2Fmcp%22%7D)

Or add to `~/.kiro/settings/mcp.json`:
```json
{
  "mcpServers": {
    "right-suite": { "url": "https://www.rightsuite.co/api/mcp" }
  }
}
```

### Gemini CLI
```bash
gemini extensions install https://github.com/wednesday-solutions/right-suite-mcp
```

### Hermes Agent
Add this to `~/.hermes/config.yaml`:
```yaml
mcp_servers:
  right-suite:
    url: "https://www.rightsuite.co/api/mcp"
    auth: oauth
```
Then run `hermes mcp login right-suite`. The [`hermes/`](hermes/) folder holds the Hermes plugin package.

### Cline
Ask Cline to set up the server from this repo; it follows [llms-install.md](llms-install.md).

### Any other MCP client
Use the server URL `https://www.rightsuite.co/api/mcp` with the Streamable HTTP transport. The
client discovers the OAuth settings from the server (dynamic client registration and client ID
metadata documents are both supported) and opens the Right Suite sign-in.

## Tools

| Tool | Read or write | What it does |
|---|---|---|
| `test_price` | Write (spends credits) | Starts a price test for an offer at a price. |
| `test_landing_page` | Write (spends credits) | Starts a test of landing page, homepage, marketing email or social copy. |
| `test_cold_email` | Write (spends credits) | Starts a test of a cold email, LinkedIn DM, X DM or community message. |
| `test_ad` | Write (spends credits) | Starts a test of ad copy and creative for Meta, Instagram, Google, YouTube, LinkedIn, TikTok or X. |
| `find_audience` | Write (spends credits) | Starts a run comparing 2 to 4 customer segments. |
| `test_positioning` | Write (spends credits) | Starts a run against 1 to 3 named competitors. |
| `pick_channel` | Write (spends credits) | Starts a run ranking 2 to 8 marketing channels. |
| `get_report` | Read | Progress, then the finished report for a run. |
| `list_runs` | Read | Your recent runs. |
| `get_credits` | Read | Your plan and credits left. |

No tool changes or deletes existing data. Run tools return a `runId` right away; reports take about
10 to 20 minutes.

## Try saying

- "I sell a Notion template pack for freelance designers at $29 one-off. Is that the right price?"
- "Here's my landing page hero: 'Ship faster with AI code review.' Will seed-stage CTOs get it?"
- "Test this cold email to heads of RevOps at 50 to 200 person SaaS companies before I send it."
- "Should I sell my analytics tool to indie hackers, agency owners or in-house growth teams first?"
- "How is my Right Suite run going?"

## Pricing

Right Suite needs a plan: Starter $4.99/month (15 credits), Growth $9.99/month (50 credits) or
Scale $19.99/month (150 credits). Each run costs 1 to 3 credits, set by its depth.

## How it works and privacy

You connect with your Right Suite account through OAuth. Right Suite only sees what you send to a
tool: the offer, copy, ad or competitor names you want tested, and who your buyers are. Simulated
buyers are generated by AI models Right Suite calls on its side. Right Suite never reads your chat
history.

- Website: https://www.rightsuite.co/mcp?utm_source=github_repo&utm_medium=directory&utm_campaign=mcp_listings
- Privacy: https://www.rightsuite.co/privacy
- Terms: https://www.rightsuite.co/terms
- Support: support@rightsuite.co

This repository holds documentation and client packages only. The server is hosted by Wednesday
Solutions; there is nothing to build or run.
