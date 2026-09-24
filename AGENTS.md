# Repository instructions

Start every session by inspecting Git status and worktrees, fetching origin with pruning, safely fast-forwarding local main, and verifying main matches origin/main. Only then create a task branch from synchronized main if needed. Preserve existing task branches and unfinished work. Never reset, discard changes, auto-stash, or force-push merely to synchronize. If safe synchronization is blocked, resolve the blocker before editing or branching.

## Code intelligence: CodeGraph

- **CodeGraph (`codegraph`) is the approved code-intelligence index.** Project-local MCP configs are committed for Claude-compatible [`.mcp.json`](.mcp.json), Codex [`.codex/config.toml`](.codex/config.toml), OpenCode [`opencode.jsonc`](opencode.jsonc), Cursor [`.cursor/mcp.json`](.cursor/mcp.json), and VS Code [`.vscode/mcp.json`](.vscode/mcp.json). Each launches `codegraph serve --mcp`, sets `CODEGRAPH_TELEMETRY=0`, and passes `--path ${workspaceFolder}` where the client supports a workspace placeholder. `AGENTS.md` stays the only instruction source; do not let an installer create a competing instruction file, and do not add or edit home-directory configs from this repo.
- **Telemetry is off** via the committed `CODEGRAPH_TELEMETRY=0`. Keep it off.
- **The index stays untracked.** `.codegraph/` is gitignored and must never be committed. Build it once per checkout, then check it:

  ```bash
  CODEGRAPH_TELEMETRY=0 codegraph init .
  CODEGRAPH_TELEMETRY=0 codegraph sync .   # after pulls or merges that add files
  CODEGRAPH_TELEMETRY=0 codegraph status   # confirm "Index is up to date"
  ```

- **Use CodeGraph for navigation, not as a source of truth.** This repository is prose-only (`SKILL.md`, `AGENTS.md`, `references/report-checklist.md`, `docs/PROJECT.md`) plus `agents/openai.yaml`; the current index contains that one YAML file and zero symbols. Use ordinary search and read for the Markdown content, and verify any CodeGraph result against the file.
- **Canonical source:** `https://github.com/colbymchenry/codegraph`. The global `codegraph` binary is a user-managed, pre-existing install (ask-first to add or update); per-repo setup here is only the wiring plus the local index. Confirm `command -v codegraph` and `codegraph version` before relying on it.
- **Commands:** `codegraph status`, `codegraph query "<symbol>"`, `codegraph node <file-or-symbol>`, `codegraph explore "<area>"`, `codegraph files`.

<!--
DOX: this AGENTS.md is organized following the DOX documentation framework at
https://github.com/agent0ai/dox (recorded revision 765ae4ac02cc884eefcd41a3d0f71941721adb89).
DOX is licensed under the MIT License, Copyright (c) 2026 Agent Zero; the upstream license text is at
https://github.com/agent0ai/dox/blob/765ae4ac02cc884eefcd41a3d0f71941721adb89/LICENSE.
No DOX text was copied verbatim into this repository.
-->
