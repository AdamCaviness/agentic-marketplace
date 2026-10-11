# Agentic Marketplace

A plugin marketplace for agentic coding tools from Adam Caviness. Claude Code registers it with `/plugin marketplace add`. Cursor can use the same Claude Code install (no second install), or a Cursor-only local plugin, or a Teams marketplace. Codex / ChatGPT desktop adds the same GitHub repo as a plugin marketplace, then installs from the directory. Gemini uses each plugin's own README.

## Plugins

- **[agentic-toolkit](https://github.com/adamcaviness/agentic-toolkit)**, skills for ticket triage, auditing, code review, and branch shipping.
- **[agentic-atlas](https://github.com/adamcaviness/agentic-atlas)**, profile an agentic workflow on 13 signed, diverging axes to see how it fits your projects.
- **[prompt-marks](https://github.com/adamcaviness/prompt-marks)**, a Claude Code mod that marks your prompts in the transcript and jumps between them. Installed with agentic-toolkit; Claude Code only.
- **[cache-handoff](https://github.com/adamcaviness/cache-magic)**, a Claude Code mod that writes a handoff while a large idle session's prompt cache is still warm, then offers to load it once the cache has gone cold. Installed with agentic-toolkit; Claude Code only. Off by default: run `/plugin configure cache-handoff@agentic-marketplace`, then set **Cache Handoff: Enabled**.

## Claude Code

```bash
/plugin marketplace add adamcaviness/agentic-marketplace
/plugin install agentic-toolkit@agentic-marketplace
/plugin install agentic-atlas@agentic-marketplace
```

Then turn on auto-update: `/plugin` → **Marketplaces** → **agentic-marketplace** → **Enable auto-update**. Claude Code leaves it off for marketplaces outside Anthropic's, so without it you keep the version you first installed.

Installing agentic-toolkit also installs its dependencies, prompt-marks and cache-handoff. To install either alone: `/plugin install prompt-marks@agentic-marketplace` or `/plugin install cache-handoff@agentic-marketplace`.

## Cursor

Pick **one** path. Installing more than one lists every skill twice.

### Already using Claude Code (recommended if you use both)

Use the Claude Code commands above. Cursor loads those plugins automatically when **Include third-party Plugins, Skills, and other configs** is on (default) in **Settings → Rules, Skills, Subagents**. Reload Cursor. Do **not** also clone into `~/.cursor/plugins/local`.

### Cursor only (Pro / individual, no Claude Code install)

```bash
mkdir -p ~/.cursor/plugins/local
git clone https://github.com/adamcaviness/agentic-toolkit.git ~/.cursor/plugins/local/agentic-toolkit
git clone https://github.com/adamcaviness/agentic-atlas.git ~/.cursor/plugins/local/agentic-atlas
```

Or symlink existing clones instead of cloning. Reload (**Developer: Reload Window**). Details: [toolkit Cursor install](https://github.com/adamcaviness/agentic-toolkit/blob/main/.cursor/INSTALL.md), [atlas Cursor install](https://github.com/adamcaviness/agentic-atlas/blob/main/.cursor/INSTALL.md).

### Cursor Teams / Enterprise

**Dashboard** is the web UI at [cursor.com/dashboard](https://cursor.com/dashboard), not a Mac app screen. Admins: **Dashboard → Plugins → Team Marketplaces** → import `https://github.com/adamcaviness/agentic-marketplace`. Teammates install from **Customize** in the sidebar.

## Codex / ChatGPT desktop

Add the marketplace, then install the plugins. Source must be `owner/repo` or a git URL, not `github.com/owner/repo`. Leave Sparse paths empty.

In **Plugins → Add plugin marketplace**:

- **Source:** `adamcaviness/agentic-marketplace`
- **Git ref:** `main`
- **Sparse paths:** empty

Then install **agentic-toolkit** and **agentic-atlas** from **Agentic Marketplace**. Restart ChatGPT / Codex if they do not appear, and start a new chat.

CLI (optional):

```bash
codex plugin marketplace add adamcaviness/agentic-marketplace --ref main
codex plugin add agentic-toolkit@agentic-marketplace
codex plugin add agentic-atlas@agentic-marketplace
```

If you previously cloned a plugin and symlinked `skills/` into `~/.agents/skills/`, remove those links first so skills do not appear twice. Details: [toolkit Codex install](https://github.com/adamcaviness/agentic-toolkit/blob/main/.codex/INSTALL.md), [atlas Codex install](https://github.com/adamcaviness/agentic-atlas/blob/main/.codex/INSTALL.md).

## License

MIT
