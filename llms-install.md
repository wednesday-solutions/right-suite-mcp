# Installing Right Suite (for AI agents)

Right Suite is a hosted remote MCP server. There is nothing to download, build or run, and no API key.

1. Add a remote MCP server named `right-suite` with:
   - URL: `https://www.rightsuite.co/api/mcp`
   - Transport: Streamable HTTP
   For Cline, add this to `cline_mcp_settings.json`:
   ```json
   {
     "mcpServers": {
       "right-suite": {
         "type": "streamableHttp",
         "url": "https://www.rightsuite.co/api/mcp"
       }
     }
   }
   ```
2. The server answers unauthenticated requests with 401 and points to its OAuth metadata. Start the OAuth sign-in when prompted; the user signs in with their Right Suite account in their browser.
3. Check the connection by calling `get_credits`. It returns the user's plan and credits left.

Troubleshooting:
- Runs need credits. If `get_credits` shows none, the user can pick a plan at https://www.rightsuite.co.
- Run tools return a `runId` right away. Runs take about 10 to 20 minutes; follow along by calling `get_report` with `waitSeconds: 45` and the `sinceCursor` it returns, and tell the user what is new after each call.
- Help: support@rightsuite.co
