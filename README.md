# Agentic Marketplace

A plugin marketplace for agentic coding tools from Adam Caviness. Claude Code registers it with `/plugin marketplace add`. Cursor can use the same Claude Code install (no second install), or a Cursor-only local plugin, or a Teams marketplace. Codex and Gemini use each plugin's own README.

## Plugins

- **[agentic-toolkit](https://github.com/adamcaviness/agentic-toolkit)**, skills for ticket triage, auditing, code review, and branch shipping.
- **[agentic-atlas](https://github.com/adamcaviness/agentic-atlas)**, profile an agentic workflow on 13 signed, diverging axes to see how it fits your projects.

## Claude Code

```bash
/plugin marketplace add adamcaviness/agentic-marketplace
/plugin install agentic-toolkit@agentic-marketplace
/plugin install agentic-atlas@agentic-marketplace
```

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

## License

MIT
