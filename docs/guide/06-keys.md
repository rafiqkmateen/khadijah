# Add, change or remove a key

Purpose: show you how to save a key so Khadijah can use an online service.
Owner: Rafiq. Version 0.3.0 (0.3.0: agreed by Rafiq, 2026-11-04; no words changed; 0.1.0 was agreed by Rafiq, 2026-11-02; the calendar key part was added after, not yet agreed). Date: 2026-11-04.

A key is a long password that lets her use an online service. She cannot answer questions until an Anthropic key or a Gemini key is saved. The other keys are optional.

Keys are saved in the Windows credential store. They are never saved in a file. A key written in `data\config.json` is ignored on purpose.

## The keys you can save

| Name to type | What it is for |
|---|---|
| `anthropic_api_key` | Her main thinking (the Claude models). |
| `gemini_api_key` | The Gemini model, if you ever pick it. |
| `tavily_api_key` | Web search. Without it she uses DuckDuckGo. |
| `google_calendar_urls` | Reading your calendar. Your calendar's private addresses go here, on one line. |
| `elevenlabs_api_key` | The online ElevenLabs voice, if you ever choose it. |

Other names the command accepts are `openai_api_key`, `copilot_api_key`, `deepseek_api_key`, `xai_api_key`, `perplexity_api_key`, `other_ai_api_key`, `broker_keys`, `webull_app_key` and `webull_app_secret`. Khadijah does not use the AI ones yet. The Webull ones are in **Webull reports**.

## Before you start

- Have the key ready, copied from the service's own website.
- Use your own terminal. Never paste a key into this chat or into any file.

## Save or change a key

1. Open a terminal.
2. Type this, using the name of the key from the table. This example saves the Anthropic key:

```powershell
cd C:\Users\you\projects\khadijah; .venv\Scripts\python.exe scripts\python\set_key.py anthropic_api_key
```

3. Paste the key at the hidden prompt and press Enter. Nothing shows as you paste. That is normal.
4. Restart Khadijah so she reads the new key.

**What you should see:** the line "Saved anthropic_api_key in the Windows credential store."

## Save the calendar's Google key

Changing calendar events needs a different kind of key. Google gives it to you as one file. Do not open it or paste it anywhere. One command reads the file, asks Google if the key works, and saves it only if Google says yes.

1. Open a terminal.
2. Type this. Put the real place of your key file where it says `<the key file>`:

```powershell
cd C:\Users\you\projects\khadijah; .venv\Scripts\python.exe scripts\python\set_key.py --calendar-file "<the key file>"
```

3. When it says Google accepted the key, open Google Calendar. Open the settings of your calendar, choose "Share with specific people", add the email address the command printed, and choose "Make changes to events".
4. Restart Khadijah.

**What you should see:** "Google accepted the key. Saved it in the Windows credential store." The key file is not changed or deleted. It is safe to keep it where it is.

If the command says "Google did not accept the key", nothing was saved. Check that it is the right file.

## Remove a key

The command cannot remove a key yet. To remove one:

1. Open **Credential Manager** from the Windows Start menu.
2. Click **Windows Credentials**.
3. Find the entry whose name ends in `@Khadijah`, for example `anthropic_api_key@Khadijah`, and remove it. The calendar's Google key is saved in several entries that start with `google_service_account`. Remove all of them.

## If it did not work

- She stops at start with "No AI key yet". Save the Anthropic key or the Gemini key as above.
- She starts, but a question gets no answer. Read **Problems and fixes**.
