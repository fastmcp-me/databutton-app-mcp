[![Add to Cursor](https://fastmcp.me/badges/cursor_dark.svg)](https://fastmcp.me/MCP/Details/835/databutton)
[![Add to VS Code](https://fastmcp.me/badges/vscode_dark.svg)](https://fastmcp.me/MCP/Details/835/databutton)
[![Add to Claude](https://fastmcp.me/badges/claude_dark.svg)](https://fastmcp.me/MCP/Details/835/databutton)
[![Add to ChatGPT](https://fastmcp.me/badges/chatgpt_dark.svg)](https://fastmcp.me/MCP/Details/835/databutton)
[![Add to Codex](https://fastmcp.me/badges/codex_dark.svg)](https://fastmcp.me/MCP/Details/835/databutton)
[![Add to Gemini](https://fastmcp.me/badges/gemini_dark.svg)](https://fastmcp.me/MCP/Details/835/databutton)

# Databutton App MCP

Use API endpoints from your Databutton app as LLM tools from any MCP compatible client!

This is a simple proxy that runs locally and connects securely to your Databutton app
using the MCP protocol over websockets.

To use it, make sure you have uv installed, see instructions here if not:

    https://docs.astral.sh/uv/getting-started/installation/

First download an API key from the settings page of your Databutton app, and save it to a file.

Then configure your LLM client (e.g. Claude Desktop or Cursor), like this:

```json
{
  "mcpServers": {
    "myDatabuttonApp": {
      "command": "uvx",
      "args": [
        "databutton-app-mcp@latest"
      ],
      "env": {
        "DATABUTTON_API_KEY": "YOUR-DATABUTTON-APP-KEY"
      }
    }
  }
}
```

or this

```json
{
  "mcpServers": {
    "myDatabuttonApp": {
      "command": "uvx",
      "args": [
        "databutton-app-mcp@latest"
        "-k",
        "/path/to/apikey.txt"
      ]
    }
  }
}
```

Here /path/to/apikey.txt is the full path to a file containing the api key,
or DATABUTTON_API_KEY is either the api key value or the path to a file containing it.
You can download the API key for your Databutton app on the app settings page.
Make sure to keep it secure and don't share it.
