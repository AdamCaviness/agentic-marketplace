# Agentic Marketplace

A plugin marketplace for agentic coding tools from Adam Caviness. Claude Code registers it with `/plugin marketplace add`. Cursor Pro (and other individual plans) install each plugin with a short `git clone` into `~/.cursor/plugins/local`. Codex and Gemini use each plugin's own README.

## Claude Code

```bash
/plugin marketplace add adamcaviness/agentic-marketplace
/plugin install agentic-toolkit@agentic-marketplace
/plugin install agentic-atlas@agentic-marketplace
```

## Cursor (Pro / individual plans)

No marketplace import in the desktop app. Paste into Terminal (requires Git), then **Developer: Reload Window**:

```bash
mkdir -p ~/.cursor/plugins/local
git clone https://github.com/adamcaviness/agentic-toolkit.git ~/.cursor/plugins/local/agentic-toolkit
git clone https://github.com/adamcaviness/agentic-atlas.git ~/.cursor/plugins/local/agentic-atlas
```

That is user-level (every project). Skills appear under `/` in Agents. Confirm in **Customize → Skills**.

Use only `~/.cursor/plugins/local` for Cursor. Do not also link the same skills into `~/.agents/skills/` or `~/.cursor/skills/`, or every skill appears twice.

Update:

```bash
git -C ~/.cursor/plugins/local/agentic-toolkit pull
git -C ~/.cursor/plugins/local/agentic-atlas pull
```

Full notes: [agentic-toolkit/.cursor/INSTALL.md](https://github.com/adamcaviness/agentic-toolkit/blob/main/.cursor/INSTALL.md).

> **Teams / Enterprise only:** admins import this repo at [cursor.com/dashboard](https://cursor.com/dashboard) → **Plugins** → **Team Marketplaces**. Teammates then install from **Customize**. Pro users use the clone path above.

## Plugins

- **[agentic-toolkit](https://github.com/adamcaviness/agentic-toolkit)**, skills for ticket triage, auditing, code review, and branch shipping.
- **[agentic-atlas](https://github.com/adamcaviness/agentic-atlas)**, profile an agentic workflow on 13 signed, diverging axes to see how it fits your projects.

## License

MIT
