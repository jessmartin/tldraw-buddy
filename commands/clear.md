---
description: Clear all shapes from the canvas (destructive — asks first)
allowed-tools: Bash
---

**Do not run the clear command immediately.**

First, run `${CLAUDE_PLUGIN_ROOT}/bin/tldraw-buddy snapshot` to see what's on the canvas.

Then tell the user what's currently there (shape count, brief description) and ask: "Clear all of this? You may want to `/tldraw-buddy:save` first."

Only after the user confirms, run `${CLAUDE_PLUGIN_ROOT}/bin/tldraw-buddy clear`.

Then say: "Here's what just happened — canvas cleared, N shapes removed."
