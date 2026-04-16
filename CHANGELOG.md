# Changelog

All notable changes to tldraw-buddy will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.2.0] — 2026-04-16

### Added
- Slash commands for common canvas operations:
  - `/tldraw-buddy:start` — start services; drops a random greeting sticky on an empty canvas
  - `/tldraw-buddy:narrate` — human-readable description of what's on the canvas
  - `/tldraw-buddy:save [file.tldr]` — save the canvas to disk
  - `/tldraw-buddy:clear` — snapshots and asks before clearing
  - `/tldraw-buddy:list` — list `.tldr` files in the repo and offer to load one via `AskUserQuestion`

## [0.1.3] — 2026-04-16

### Fixed
- Skill now loads correctly — moved from `skills/tldraw.md` to `skills/tldraw/SKILL.md` to match Claude Code's expected plugin layout. Previously the skill was silently skipped (`/reload-plugins` reported 0 skills).
- Bash syntax error in `bin/tldraw-buddy start` (env-var prefix on a subshell) that prevented the script from running.

## [0.1.2] — 2026-04-16

### Changed
- **Breaking:** Marketplace renamed from `sociotechnica` to `jessmartin`. Existing users must remove the old marketplace and re-add under the new name:
  ```
  claude plugin marketplace remove sociotechnica
  claude plugin marketplace add jessmartin/tldraw-buddy --scope user
  claude plugin install tldraw-buddy@jessmartin --scope user
  ```

### Added
- `npm run validate` script (runs `claude plugin validate .`) plus CI validation of the plugin manifest on every push/PR.

## [0.1.1] — 2026-04-16

### Fixed
- Plugin manifest `author` field is now an object (`{name, url}`) instead of a string, so `claude plugin install` no longer fails with "Author: invalid input, expected object, received string".

## [0.1.0] — 2026-04-10

Initial release.

### Added
- Shared tldraw canvas for AI agents, with CLI + Skill for Claude Code integration.
- CLI commands: `snapshot`, `create`, `connect`, `update`, `delete`, `clear`, `save`, `load`.
- Persistent canvas state across browser sessions (IndexedDB).
- Save/load `.tldr` files on disk for committing drawings alongside code.
- Dynamic port allocation — no more conflicts on 5173 or 4000.
- Role-aware WebSocket relay to prevent duplicate shapes.
- tldraw-buddy logo (with pupils — the buddies can see).
- Plugin marketplace install as the primary install method.
- README with install, config, and update instructions.

### Changed
- Refactored from MCP server to CLI + Skills architecture.
- Renamed project from `tldraw-claude` to `tldraw-buddy`.

### Fixed
- Duplicate shapes — role-aware relay and removed React StrictMode double-rendering.
- Geo shape text rendering on tldraw v4 (`text` → `richText`).
- Setup script install path.
