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
- Run tools return a `runId` right away; call `get_report` with it after a few minutes. Runs take about 10 to 20 minutes.
- Help: support@rightsuite.co
