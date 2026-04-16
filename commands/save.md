---
description: Save the canvas to a .tldr file
argument-hint: "[filename.tldr]"
allowed-tools: Bash
---

Run `${CLAUDE_PLUGIN_ROOT}/bin/tldraw-buddy save $ARGUMENTS`.

If no argument is given, it saves to `canvas.tldr` in the current directory.

Then tell the user: "Here's what just happened!" and confirm:
- What file was written (path + size if easy to tell)
- One line on what they can do next — commit it, reload with `/tldraw-buddy:load`, share the file

Keep it to 2–3 short lines.
