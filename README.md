# Agentic Marketplace

Adam's plugin marketplace for agentic coding tools. Intended to support Claude Code, ChatGPT (Codex), Devin, Cursor, and Antigravity.

## Plugins

- **[agentic-toolkit](https://github.com/adamcaviness/agentic-toolkit)**, skills for ticket triage, auditing, code review, and branch shipping.
- **[agentic-atlas](https://github.com/adamcaviness/agentic-atlas)**, profile an agentic workflow on 13 signed, diverging axes to see how it fits your projects.
- **[prompt-marks](https://github.com/adamcaviness/prompt-marks)**, a Claude Code mod that marks your prompts in the transcript and jumps between them. Installed with agentic-toolkit; Claude Code only.
- **[cache-magic](https://github.com/adamcaviness/cache-magic)**, a Claude Code mod that writes a handoff while a large idle session's prompt cache is still warm, then sends a prompt that arrives after it expired with the handoff instead of the full context. Installed with agentic-toolkit; Claude Code only. Settings are the "Cache Magic" rows in `/config`.

## Claude Code

Supported: add this marketplace, then install from it.

```bash
/plugin marketplace add adamcaviness/agentic-marketplace
/plugin install agentic-toolkit@agentic-marketplace
/plugin install agentic-atlas@agentic-marketplace
```

Each `/plugin install` opens the plugin's details; pick a scope to finish. From your shell, `claude plugin marketplace add` and `claude plugin install` take the same arguments.

Then turn on auto-update: `/plugin` → **Marketplaces** → **agentic-marketplace** → **Enable auto-update**. Claude Code leaves it off for marketplaces outside Anthropic's, so without it you keep the version you first installed.

Installing agentic-toolkit also installs its dependencies, prompt-marks and cache-magic. To install either alone: `/plugin install prompt-marks@agentic-marketplace` or `/plugin install cache-magic@agentic-marketplace`.

cache-handoff was renamed cache-magic. If you have cache-handoff installed, run `/plugin uninstall cache-handoff@agentic-marketplace`.

## ChatGPT (Codex)

Supported in the ChatGPT desktop app and the Codex CLI. The Codex IDE extension doesn't support plugins.

Add the marketplace, then install the plugins. Source must be `owner/repo` or a git URL, not `github.com/owner/repo`. Leave Sparse paths empty.

In **Plugins → Add plugin marketplace**:

- **Source:** `adamcaviness/agentic-marketplace`
- **Git ref:** `main`
- **Sparse paths:** empty

Then install **agentic-toolkit** and **agentic-atlas** from **Agentic Marketplace**. Restart ChatGPT if they do not appear, and start a new chat.

CLI (optional):

```bash
codex plugin marketplace add adamcaviness/agentic-marketplace --ref main
codex plugin add agentic-toolkit@agentic-marketplace
codex plugin add agentic-atlas@agentic-marketplace
```

Refresh with `codex plugin marketplace upgrade agentic-marketplace`. If you previously cloned a plugin and symlinked `skills/` into `~/.agents/skills/`, remove those links first so skills do not appear twice.

## Devin

Partly supported: Devin has no add-a-marketplace step. Installing this repo installs a plugin that lists ours as optional plugins without installing them.

```bash
devin plugins install adamcaviness/agentic-marketplace
devin plugins info agentic-marketplace
devin plugins install adamcaviness/agentic-toolkit
devin plugins install adamcaviness/agentic-atlas
```

`devin plugins info` shows the optional plugins; install the ones you want. Plugins install to your personal scope, so they follow you to the CLI, Devin Desktop, and cloud sessions. Requires `devin auth login`. Update with `devin plugins update`.

On the web, open **Customize → Plugins → Add plugin → From repository** and enter a plugin's repository, such as `adamcaviness/agentic-toolkit`. Organization and enterprise scopes need an admin.

## Cursor

Partly supported: the Cursor CLI and Teams / Enterprise can add this marketplace. The Cursor app has no way for an individual to add a marketplace; see **Cursor app, individual plan** below.

Pick **one** path. Installing more than one lists every skill twice.

### Already using Claude Code

Install with the Claude Code commands above. Cursor loads Claude Code plugins while **Include Third-Party Plugins, Skills, and Other Configs** is on (the default) in **Cursor Settings → Agents → Third-Party Imports**. Reload Cursor.

### Cursor CLI

```bash
agent plugin marketplace add https://github.com/adamcaviness/agentic-marketplace
agent
```

In the session, run `/plugin`, open this marketplace, and install **agentic-toolkit** and **agentic-atlas**.

### Cursor Teams / Enterprise

An admin opens **Dashboard → Plugins & MCPs** at [cursor.com/dashboard](https://cursor.com/dashboard), selects **Add Marketplace** under **Team Marketplaces**, and imports `https://github.com/adamcaviness/agentic-marketplace` with **Import from Repo**. Teammates install from **Customize** in the sidebar.

### Cursor app, individual plan

Without the Claude Code path above, install each plugin from its own repository. Follow the install section of its README: [agentic-toolkit](https://github.com/adamcaviness/agentic-toolkit#installation), [agentic-atlas](https://github.com/adamcaviness/agentic-atlas#plugin-installation). Skip prompt-marks and cache-magic; they only work in Claude Code.

## Antigravity

Not supported: Antigravity can't add marketplaces other than Google's official `antigravity-plugins-official`.

Install each plugin, or just its skills, from its own repository instead. Follow the install section of its README: [agentic-toolkit](https://github.com/adamcaviness/agentic-toolkit#installation), [agentic-atlas](https://github.com/adamcaviness/agentic-atlas#plugin-installation). Skip prompt-marks and cache-magic; they only work in Claude Code.

## License

MIT
