# Where she keeps things

Purpose: tell you which files Khadijah writes, where they are, and which you may delete.
Owner: Rafiq. Version 0.1.1 (agreed by Rafiq, 2026-11-02). Date: 2026-11-02.

Everything is inside the Khadijah folder, `C:\Users\you\projects\khadijah`.

When she saves a file, she writes it to a temporary file first and then swaps it in. A crash cannot leave half a file.

## What is where

| What | Where | Notes |
|---|---|---|
| Her settings | `data\config.json` | Yours. Do not paste it anywhere. |
| Your tasks | `user-tasks\Tasks.md` | Yours. |
| Your notes | `data\notes` | Yours. Notes saved with "remember that" are in `captures`. |
| What she heard when you wake her | `data\activation-heard.txt` | Keeps the newest 200 lines. Shows how she mishears you. |
| Web search count | `data\tavily-usage.json` | Holds only the month and the count. |
| Her listening model | `data\whisper-models` | About 460 MB. Downloaded the first time you use it. |
| Her voice sample | `voice\personal-voice` | `sample.wav` and `sample.txt`. Kept out of Git. |
| Her pictures and face video | `frontend\backgrounds`, `frontend\logos`, `frontend\faces` | Kept out of Git. |
| Your WhatsApp names and reply languages | `data\wa-contacts.json`, `data\wa-lang.json` | Yours. Do not delete the names. |
| Your trusted network devices | `data\known-devices.json` | Yours. Without it every device looks new. |
| Your saved missions | `data\missions.json` | Yours. |
| What you follow in Google News | `data\google-news-follow.json` | Yours. |
| The dollar-to-peso history | `data\fx-history.json` | Built again if deleted. |
| Your Claude plan limits | `data\claude-limits.json` | Built again if deleted. |
| The morning brief and patch check records | `data\briefing_state.json`, `data\brief-rates.json`, `data\patch-check-state.json`, `data\patch-check-history.json`, `data\patch-snapshots`, `data\patch-update-notice.json` | Built again if deleted. |
| Her log | `logs\assistant_server.log` | See below. |

## The log

The log keeps a copy of everything the server prints. It helps you find out what went wrong after a restart.

- When it reaches 5 MB, it is renamed and a new one starts.
- Three older logs are kept. The oldest is dropped.

**Safe to delete:** yes. Stop her first. She makes a new one.

## Do not delete

Do not delete your notes, your tasks file, your settings, her voice sample or her pictures, unless you mean to. They are yours, and some cannot be remade from the project.
