# Agentic Marketplace

A plugin marketplace for agentic coding tools from Adam Caviness. Claude Code registers it with `/plugin marketplace add`. Cursor desktop loads each plugin from `~/.cursor/plugins/local` (or from a Team Marketplace on Teams/Enterprise plans). Codex and Gemini use each plugin's own README.

## Register / install

### Claude Code

```bash
/plugin marketplace add adamcaviness/agentic-marketplace
/plugin install agentic-toolkit@agentic-marketplace
/plugin install agentic-atlas@agentic-marketplace
```

### Cursor (desktop)

Cursor desktop does not import this repo from a "Dashboard" inside the app. **Dashboard → Plugins** is the [web Teams/Enterprise admin UI](https://cursor.com/dashboard), not a Mac app screen.

**Individual install** (Hobby / Pro, or anyone not using a team marketplace): symlink each plugin repo into `~/.cursor/plugins/local`, then reload the window:

```bash
mkdir -p ~/.cursor/plugins/local
git clone https://github.com/adamcaviness/agentic-toolkit.git ~/opensource/agentic-toolkit
git clone https://github.com/adamcaviness/agentic-atlas.git ~/opensource/agentic-atlas
ln -s ~/opensource/agentic-toolkit ~/.cursor/plugins/local/agentic-toolkit
ln -s ~/opensource/agentic-atlas ~/.cursor/plugins/local/agentic-atlas
```

Skills appear under `/` in Agents. Confirm in **Customize → Skills**.

**Teams / Enterprise only:** an admin imports this repository at [cursor.com/dashboard](https://cursor.com/dashboard) → **Plugins** → **Team Marketplaces** → **Add Marketplace** / **Import from Repo** (`https://github.com/adamcaviness/agentic-marketplace`). Teammates then install plugins from **Customize** in the Cursor sidebar.

## Plugins

- **[agentic-toolkit](https://github.com/adamcaviness/agentic-toolkit)**, skills for ticket triage, auditing, code review, and branch shipping.
- **[agentic-atlas](https://github.com/adamcaviness/agentic-atlas)**, profile an agentic workflow on 13 signed, diverging axes to see how it fits your projects.

## License

MIT
