---
description: List .tldr files in the repo and optionally load one
allowed-tools: Bash, AskUserQuestion
---

`.tldr` files found in the current directory:

```!
find . -type f -name "*.tldr" -not -path "*/node_modules/*" -not -path "*/.git/*" 2>/dev/null | sort
```

1. If the list above is empty, tell the user and suggest they draw something or `/tldraw-buddy:save` their current canvas. Stop.

2. Otherwise, use `AskUserQuestion` to present the files as options, plus a "Don't load anything" option to back out.

3. If they pick a file, run `${CLAUDE_PLUGIN_ROOT}/bin/tldraw-buddy load <path>`, then say: "Here's what just happened — loaded `<file>` onto the canvas." Follow up with a one-line narration of what's now on the canvas (use `${CLAUDE_PLUGIN_ROOT}/bin/tldraw-buddy snapshot`).

4. If they pick "Don't load anything", acknowledge and stop.
