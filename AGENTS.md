## UI components

This project sources UI from Systra Tools over MCP.

Before writing a new section by hand, search the library:
`search_components` with the intent in plain words, then `get_component`
for the source. Paste what comes back rather than paraphrasing it.

For a complete page, `list_recipes` and then `get_recipe` return an ordered
sequence of sections that belong together.

To match this project's brand, `list_styles` and `get_component_styled`
return the same component already in those colours and fonts.

Everything is React, TypeScript and Tailwind with no runtime dependency on
Systra. Once a component is pasted, it is this project's code.
