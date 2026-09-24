# Clarify First

[简体中文说明](README.zh-CN.md)

Clarify First is a reusable, opt-in workflow for AI assistants. It asks one useful question at a time when a task is unclear, confirms the user's goal and approach, and then completes the original task. Clear requests can go straight to confirmation. The workflow applies to one task and has no fixed question limit.

The reusable behavior lives in [`SKILL.md`](plugins/clarify-first/skills/clarify-first/SKILL.md). The surrounding files package it as a skills-only plugin for ChatGPT/Codex. There is no MCP server, account connection, or external runtime dependency.

## Quick start

Use your host's explicit skill command with the task in the same message:

| Host | Example |
| --- | --- |
| Codex | `$clarify-first Help me plan and build a portfolio site.` |
| ChatGPT Work | Select the `clarify-first` skill, then enter `Help me plan and build a portfolio site.` |
| Claude Code | `/clarify-first Help me plan and build a portfolio site.` |
| Other chat models | Configure [PROMPT.md](PROMPT.md), then enter `clarify-first: Help me plan and build a portfolio site.` |

If you invoke the skill without a task, the assistant will ask what you want to work on. The “98% confidence” idea is a high-confidence judgment, not a numerical guarantee.

## Install

Download or clone this repository first. The plugin package is at `plugins/clarify-first/`.

### Codex and ChatGPT desktop

The repository includes a Codex marketplace file at `.agents/plugins/marketplace.json`. From a terminal with Codex installed, add the cloned repository as a marketplace:

```text
codex plugin marketplace add <absolute-path-to-this-repository>
```

Or add the public GitHub repository directly:

```text
codex plugin marketplace add jackmiao-svg/clarify-first
```

Restart the desktop app, open the Plugins Directory, choose the Clarify First marketplace, and install the plugin. In Codex CLI, open `/plugins` and install it from the added marketplace. Start a new conversation after installation.

GitHub distribution through a marketplace and publication in the official ChatGPT/Codex public Plugins Directory are separate processes. Public directory listing requires a submission and review.

For the official directory, see the [submission notes and reviewer test cases](SUBMISSION.md).

### Claude Code

Copy `plugins/clarify-first/skills/clarify-first/` into `~/.claude/skills/clarify-first/` for personal use, or `.claude/skills/clarify-first/` in a project. Then invoke `/clarify-first` with a task. Claude Code ignores the OpenAI-specific `agents/openai.yaml` file.

### Gemini CLI

From this repository's root, link the skill directory:

```text
gemini skills link ./plugins/clarify-first/skills/clarify-first
```

Use `/skills list` to check discovery. Gemini CLI may ask for activation consent when the skill is used.

### Models without Agent Skills

Use the [standalone prompt](PROMPT.md) in custom instructions or at the start of a conversation. The command by itself cannot configure an unprepared model.

## What to expect

1. The assistant uses information already in the request and conversation.
2. If a meaningful gap remains, it asks one question and waits for the answer.
3. It presents an understanding summary and proposed approach for confirmation.
4. After confirmation, it carries out the original task and reports the result.

## Project layout

```text
.agents/plugins/marketplace.json           Codex marketplace listing
plugins/clarify-first/plugin.json           Portable plugin manifest
plugins/clarify-first/.codex-plugin/         Codex compatibility manifest
plugins/clarify-first/skills/clarify-first/  Agent Skill
PROMPT.md                                    Standalone prompt for other models
LICENSE                                      MIT license
```

## License

MIT. See [LICENSE](LICENSE).
