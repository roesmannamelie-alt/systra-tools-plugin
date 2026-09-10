<p align="center">
  <img src="logo.png" width="88" alt="Systra Tools">
</p>

<h1 align="center">Systra Tools</h1>

<p align="center">
  620+ production-ready React + Tailwind sections and elements,<br>
  searchable by your coding agent over MCP.
</p>

<p align="center">
  <a href="cursor://anysphere.cursor-deeplink/mcp/install?name=systra-tools&config=eyJ1cmwiOiJodHRwczovL3N5c3RyYS50b29scy9hcGkvbWNwIiwiaGVhZGVycyI6eyJBdXRob3JpemF0aW9uIjoiQmVhcmVyICR7ZW52OlNZU1RSQV9NQ1BfS0VZfSJ9fQ=="><img src="https://cursor.com/deeplink/mcp-install-dark.png" alt="Add systra-tools to Cursor" height="32"></a>
</p>

---

Your AI can code. It just has no taste. This plugin gives it a source of
finished UI instead of another purple gradient: 37 categories, 18 page
recipes, and a style extractor that recolours any component to match a real
brand. Everything is React, TypeScript and Tailwind with no runtime
dependency, so once a component lands in your project it is your code.

## Install

### Cursor

Click the button above, or add the plugin from
[cursor.directory](https://cursor.directory), or configure it by hand in
`~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "systra-tools": {
      "url": "https://systra.tools/api/mcp",
      "headers": { "Authorization": "Bearer ${env:SYSTRA_MCP_KEY}" }
    }
  }
}
```

### Claude Code

```
/plugin marketplace add roesmannamelie-alt/systra-tools-plugin
/plugin install systra-tools@systra
```

### VS Code, Windsurf and anything else that speaks MCP

Point an HTTP MCP server at `https://systra.tools/api/mcp` and send your key
as `Authorization: Bearer <key>`.

## Your key

Create one at [systra.tools/mcp](https://systra.tools/mcp) and put it in the
environment as `SYSTRA_MCP_KEY`. A free account reaches a limited set of
components, full access needs Premium. Do not commit the key.

## What the agent gets

| Tool | What it does |
| --- | --- |
| `list_categories` | 37 categories with counts |
| `list_components`, `search_components` | find a section by intent |
| `get_component` | the full source |
| `list_recipes`, `get_recipe` | an ordered page, 18 recipes |
| `list_styles`, `get_style`, `get_component_styled` | the same component in a real brand's colours and fonts |
| `list_images`, `search_images` | imagery with permanent URLs |
| `list_posts`, `get_post` | social post templates |

Largest categories: elements (78), heroes (76), features (38), interaktiv
(29), gallery (25), gsap (22), stats (22), trust (19), dashboard (18).

## What is in this repository

A rule, two skills and the MCP configuration. That is all a plugin is. The
component library itself lives behind the MCP server.

MIT for the configuration in this repository. The library is licensed
separately, see [systra.tools](https://systra.tools).
