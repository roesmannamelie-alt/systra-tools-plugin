---
name: setup
description: Set up the Systra Tools MCP server, including the personal key. Use when Systra tool calls fail with an authorisation error or the user is installing the plugin for the first time.
---

# Setting up Systra Tools

The Systra MCP server is reached over HTTPS and authenticates with a personal
key in the `Authorization` header.

## Steps

1. Ask the user to open https://systra.tools/mcp and copy their key. A free
   account reaches a limited set of components, full access needs Premium.
2. Put the key in the environment rather than in a file that gets committed:

   ```
   export SYSTRA_MCP_KEY="..."
   ```

   On Windows, set it as a user environment variable of the same name.
3. Restart the editor so the MCP server picks the variable up.
4. Verify with `list_categories`. It should return 37 categories. If it
   returns an authorisation error, the key is missing or wrong.

## Configuration reference

```json
{
  "mcpServers": {
    "systra-tools": {
      "url": "https://systra.tools/api/mcp",
      "headers": { "Authorization": "Bearer ${SYSTRA_MCP_KEY}" }
    }
  }
}
```

Never write the key itself into a file inside the repository, and never echo
it back into the conversation.
