---
description: Show what's currently on the tldraw canvas
allowed-tools: Bash
---

Run `${CLAUDE_PLUGIN_ROOT}/bin/tldraw-buddy snapshot`.

Then tell the user: "Here's what's on the canvas!" and give them a concise human-readable summary — shape count, what's there (e.g. "3 rectangles connected by arrows, looks like a flowchart"), not a raw JSON dump.

If the canvas is empty, say so and suggest what they could ask you to draw.

If the connection fails, tell them the widget isn't running and to try `/tldraw-buddy:start`.
