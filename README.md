# Agentic Marketplace

A plugin marketplace for agentic coding tools from Adam Caviness. It is a peer install source for Claude Code and Cursor (and documents the same plugins for Codex and Gemini via each plugin's own README).

## Register the marketplace

**Claude Code**

```bash
/plugin marketplace add adamcaviness/agentic-marketplace
```

**Cursor**

1. Open **Dashboard → Plugins → Team Marketplaces** (or **Customize → Plugins**).
2. Import `https://github.com/adamcaviness/agentic-marketplace`.

## Plugins

- **[agentic-toolkit](https://github.com/adamcaviness/agentic-toolkit)**, skills for ticket triage, auditing, code review, and branch shipping.
- **[agentic-atlas](https://github.com/adamcaviness/agentic-atlas)**, profile an agentic workflow on 13 signed, diverging axes to see how it fits your projects.

## Install a plugin

**Claude Code**

```bash
/plugin install agentic-toolkit@agentic-marketplace
/plugin install agentic-atlas@agentic-marketplace
```

**Cursor**

After importing the team marketplace, install **agentic-toolkit** and **agentic-atlas** at user or project scope from Customize → Plugins. Skills appear under `/` in the Agents window.

## License

MIT
