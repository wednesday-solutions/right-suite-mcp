---
name: right-suite
description: Test a price, landing page, cold email, ad, positioning, audience or channel on simulated buyers with Right Suite, then read the report. Use when the user asks "is my price right", "what should I charge", "roast my landing page", "will this cold email get replies", "will this ad work", "who should I sell to first", "how do I stand out from X", or "which channel should I bet on", or asks about a Right Suite run or their credits.
---

# Right Suite

Every tool named below comes from Right Suite's hosted MCP server, `https://www.rightsuite.co/api/mcp`,
which this plugin adds as `right-suite`. Each run shows the user's own offer, copy or ad to 100+
simulated buyers modelled on the audience they describe, and returns a report.

If the tools are missing or a call says the user is not signed in, the server needs its one-time
sign-in: tell the user to connect or authenticate the `right-suite` MCP server in their app's MCP
settings and sign in with their Right Suite account. Do not try to sign in for them.

## Pick the tool

| The user wants to know | Tool |
|---|---|
| Would buyers pay this price? What should I charge? | `test_price` |
| Does my landing page, homepage, marketing email or post land? | `test_landing_page` |
| Will this cold email or DM get a reply? | `test_cold_email` |
| Will this ad stop the scroll and get the click? | `test_ad` |
| Which customer segment should I sell to first? | `find_audience` |
| Why would buyers pick me over competitors? | `test_positioning` |
| Which marketing channel should I bet on? | `pick_channel` |

Writing copy is not testing it. If the user only asks you to write a cold email, a landing page or
an ad, write it yourself; offer to test the draft with Right Suite afterwards.

## Before a run

1. Get the facts the tool needs from the user: the offer or copy exactly as it will be shown, and who
   the buyers are (role, company size, situation). Ask one short question if the audience is vague.
   Don't invent a price, competitor or audience.
2. Runs spend the user's Right Suite credits: `depth` 1, 2 or 3 costs that many credits. Use depth 1
   unless the user asks for a deeper run. If you are unsure they have credits, call `get_credits`
   first.
3. Tell the user what you are about to test and at what depth before you start a run.

## During and after a run

- A run tool returns a `runId` right away. Runs take about 10 to 20 minutes. Tell the user that,
  and that you can check on it whenever they like.
- Call `get_report` with the `runId` to check progress or fetch the finished report. Do not poll in
  a tight loop; check when the user asks or after a few minutes.
- If you lost the `runId`, call `list_runs`.
- When the report is ready, lead with the verdict, then the top objections, then the changes to
  make, in plain words. Give the dashboard link for the full report.

## Plain words

Reply in short, plain sentences. Say what was tested and what buyers said, not how the tools work.
Do not show the user tool names, ids or JSON unless they ask.

## Done when

- The user knew what would be tested and what it costs before any run started.
- The user has the verdict, the main objections and what to change, or knows when to check back.
