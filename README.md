# abtop

**Like htop, but for your AI coding agents.**

See every Claude Code and Codex CLI session at a glance — token usage, context window %, rate limits, child processes, open ports, and more.

![demo](demo.gif)

## Why

- Running 3+ agents across projects? See them all in one screen.
- Hitting rate limits? Watch your quota in real-time.
- Agent spawned a server and forgot to kill it? Orphan port detection.
- Context window filling up? Per-session % bars with warnings.

All read-only. No API keys. No network calls.

## Install

### macOS / Linux

```bash
curl --proto '=https' --tlsv1.2 -LsSf https://github.com/graykode/abtop/releases/latest/download/abtop-installer.sh | sh
```

### Windows

```powershell
powershell -ExecutionPolicy ByPass -c "irm https://github.com/graykode/abtop/releases/latest/download/abtop-installer.ps1 | iex"
```

### Cargo

```bash
cargo install abtop
```

### Other

Pre-built binaries for all platforms are available on the [GitHub Releases](https://github.com/graykode/abtop/releases) page.

## Usage

```bash
abtop          # Launch TUI
abtop --once   # Print snapshot and exit
abtop --setup  # Install rate limit collection hook
```

## Supported Agents

| Feature | Claude Code | Codex CLI |
|---------|:-----------:|:---------:|
| Session Discovery | ✅ | ✅ |
| Token Tracking | ✅ | ✅ |
| Context Window % | ✅ | ✅ |
| Status Detection | ✅ | ✅ |
| Current Task | ✅ | ✅ |
| Rate Limit | ✅ | ✅ |
| Git Status | ✅ | ✅ |
| Children / Ports | ✅ | ✅ |
| Subagents | ✅ | ❌ |
| Memory Status | ✅ | ❌ |

## Key Bindings

| Key | Action |
|-----|--------|
| `↑`/`↓` or `k`/`j` | Select session |
| `Enter` | Jump to session terminal (tmux only) |
| `Tab` | Cycle focus between panels |
| `1`–`4` | Toggle panel visibility |
| `q` | Quit |
| `r` | Force refresh |

## Privacy

abtop reads local files only. No network calls, no API keys, no auth. Tool names and file paths are shown in the UI, but file contents and prompt text are never displayed.

## License

MIT
