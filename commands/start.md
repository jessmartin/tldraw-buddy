---
description: Start the tldraw canvas and WS relay
allowed-tools: Bash
---

1. Run `${CLAUDE_PLUGIN_ROOT}/bin/tldraw-buddy start` and wait for it to complete.

2. Once the widget and WS relay are up (give it a second if just started), run `${CLAUDE_PLUGIN_ROOT}/bin/tldraw-buddy snapshot` to check the canvas.

   **Only if the canvas is empty** (no shapes), pick ONE random greeting from this list and drop it on the canvas as a sticky note. If the canvas already has shapes, skip the greeting — don't clutter the user's work.

   Greetings:
   - "hi there! 👋"
   - "ready to draw!"
   - "let's make something cool"
   - "heyyy — tldraw buddy reporting for duty"
   - "canvas is live, what are we drawing?"
   - "oh hi! i brought pens"
   - "draw something weird with me"

   Pick a random color for the note from: yellow, orange, light-green, light-blue, violet, light-red.

   Then run: `${CLAUDE_PLUGIN_ROOT}/bin/tldraw-buddy create --type note --x 100 --y 100 --text "<greeting>" --color <color>`

3. Then tell the user: "Here's what just happened!" with 3–4 short lines covering:
   - Whether services started (or were already running)
   - The canvas URL from the output
   - Either: you dropped a greeting on the canvas (if it was empty), OR: canvas already had work so you left it alone

If the start command fails, report the error and skip the greeting.
