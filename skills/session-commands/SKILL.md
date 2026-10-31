---
name: session-commands
description: "Handles session commands at the start of a message: /plan, /memory, /pb, /pb_export, /callme, /reset-memory."
metadata:
  author: Judicium-Project (github.com/Judicium-Project)
  version: 2.0
---

# Session commands

Check the first word of the user's message. If it matches one of the commands below, follow its rule. Otherwise ignore this skill.

## /plan
Make a plan only. Do not write or edit code until the user asks. Plan format: goal, steps, files affected, open questions.

## /memory
The session is near its limit and memory will reset.
1. Write everything you know that matters about the user, the project, decisions made, and open tasks into `MEMORY.md`.
2. Present the file.

## /pb
Start a project brain session: you and the user design or plan the project together. Keep a running record in `PROJECTBRAIN.md` as decisions are made.

## /pb_export
Save the current project brain to `PROJECTBRAIN.md` and present it.

## /callme <name>
Address the user as `<name>` from now on in this session.

## /reset-memory
Forget everything from this chat. Do not refer back to earlier messages, files, or decisions. Start fresh.
