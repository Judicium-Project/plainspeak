<p align="center">
  <img src="https://github.com/Judicium-Project/plainspeak/blob/img/plainspeak-banner(1).png?raw=true" alt="plainspeak banner" width="100%">
</p>

<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-JP--NC--A%201.0-lightgrey.svg" alt="License: JP-NC-A 1.0"></a>
  <a href="https://github.com/Judicium-Project/plainspeak/releases"><img src="https://img.shields.io/github/downloads/Judicium-Project/plainspeak/total.svg" alt="Downloads"></a>
  <a href="https://github.com/Judicium-Project/plainspeak/stargazers"><img src="https://img.shields.io/github/stars/Judicium-Project/plainspeak.svg?style=social" alt="Stars"></a>
  <a href="https://github.com/Judicium-Project/plainspeak/commits"><img src="https://img.shields.io/github/last-commit/Judicium-Project/plainspeak.svg" alt="Last commit"></a>
</p>

# plainspeak

Two skills for Claude. **plainspeak** keeps replies, code, and websites direct and free of filler. **session-commands** handles a handful of slash commands for planning, memory, and project notes.

## What it changes

Without it, Claude tends to open with a compliment, restate your question, pile on caveats, and close with a summary. With plainspeak loaded, the answer comes first and stops when the task is done.

| Before | After |
|---|---|
| "Great question! Let me walk you through how caching works. First, ..." | "Caching stores the response for reuse. Set `Cache-Control: max-age=300` to keep it five minutes." |
| "I'd be happy to help. Here are a few options you might consider: ..." | One recommendation, with the reason. |
| A 400-word essay for a yes/no question | "Yes. The flag is `--force`." |

The rules still keep the details that matter. Commands, file paths, error messages, and anything needed for correctness stay exact. Plainspeak cuts padding, not information.

## Skills

**plainspeak**
- Applies to chat replies, code, file edits, reviews, drafts, and websites.
- Sets a priority order: correctness and safety first, then your instructions, then completeness, then brevity.
- Keeps a casual chat voice (short words, lowercase) for casual chat only. Technical content, code, and written deliverables stay in normal language.
- Loads reference checklists only when they're needed:
  - `references/web-quality.md`: content, accessibility, SEO, performance
  - `references/security-privacy.md`: secrets, auth, input handling, personal data
  - `references/code-quality.md`: structure, errors, dependencies, verification
  - `references/i18n.md`: translations, locale formatting, right-to-left text

**session-commands**
- `/plan`: plan only, no code until you ask.
- `/memory`: save what matters to `MEMORY.md` before the session limit resets it.
- `/pb`: start a project brain session. Decisions go in `PROJECTBRAIN.md`.
- `/pb_export`: save and present the project brain.
- `/callme <name>`: address you by that name for the session.
- `/reset-memory`: drop everything from the chat and start fresh.

## Install

### Claude.ai (Pro, Max, Team, or Enterprise)

1. Download `plainspeak-repo.zip` from the [releases page](https://github.com/Judicium-Project/plainspeak/releases) and unzip it.
2. Open **Settings > Capabilities > Skills**.
3. Click **Upload skill** and select `plainspeak.skill`. Repeat for `session-commands.skill`.
4. Make sure code execution is enabled under **Settings > Capabilities**.

Claude.ai limits skill descriptions to 200 characters. Both descriptions in this release fit that limit.

Custom skills are personal to your account. On Team or Enterprise, an admin can provision a skill for the whole organization.

### Claude Code

Copy the folders into your skills directory:

```bash
mkdir -p ~/.claude/skills
cp -r skills/plainspeak skills/session-commands ~/.claude/skills/
```

Start a new session. The skills load when a task matches their descriptions.

## How triggering works

A skill loads when Claude decides the task matches its description. Simple one-line questions may not trigger it. Longer writing, code, and review tasks do. The reference files load only when the task needs them.

If plainspeak doesn't seem to apply, check that it is enabled and that the request is long enough to need it. You can also name it directly, for example "use plainspeak for this."

## Customizing

Edit `skills/plainspeak/SKILL.md` to change the core rules. Edit or add files in `references/` for domain checklists. Keep each `SKILL.md` description under 200 characters if you plan to upload to claude.ai.

To build the installable files from the folders, zip each skill folder and rename the archive to `.skill`:

```bash
cd skills
zip -r plainspeak.skill plainspeak
zip -r session-commands.skill session-commands
```

## Repository layout

```
plainspeak/
├── README.md
├── LICENSE
└── skills/
    ├── plainspeak/
    │   ├── SKILL.md
    │   └── references/
    │       ├── web-quality.md
    │       ├── security-privacy.md
    │       ├── code-quality.md
    │       └── i18n.md
    └── session-commands/
        └── SKILL.md
```

## Contributing

Issues and suggestions are welcome. For changes to the rules, open an issue first with a short example of the output you expected and the output you got.

Forks and modified versions are covered by the license below. Please keep the attribution and mark your changes.

## License

JP-NC-A 1.0. Noncommercial use, modification, and republishing are allowed with attribution to Judicium-Project. Commercial use needs written permission. See [LICENSE](LICENSE).

Copyright (c) 2026 Judicium-Project. [github.com/Judicium-Project](https://github.com/Judicium-Project)
