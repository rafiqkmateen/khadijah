# Morning brief

Purpose: tell you what the morning brief is, when it comes, and how to send a test.
Owner: Rafiq. Version 0.2.0 (0.2.0: agreed by Rafiq 2026-11-03, with times in military time and the test command fixed to curl.exe; 0.1.1: draft). Date: 2026-11-03.

Every morning she sends you one WhatsApp message with your day and Cartagena's news. It only reads. It needs WhatsApp paired (see the WhatsApp page) and a place to send to.

## What it holds

- **Today on your calendar:** up to five events, then "and N more".
- **Open tasks:** up to five, then "and N more".
- **Your recent notes:** up to two voice notes from the last seven days.
- **Weather alert:** only when the weather is dangerous.
- **Local alerts:** up to three, such as a water cut or a storm warning.
- **Dollar to peso:** today's rate and how far it moved since the last reading.
- **Festivals and events:** up to two.

A part that could not be read is left out. A part with nothing in it says so ("nothing scheduled", "none open", "none today").

## When it comes

1. At 0700.
2. If she was off at 0700, she sends it when she starts before 1100.
3. Never twice in one day. If WhatsApp is off, that day counts as tried and she does not send it later.
4. If the send fails she tries again every minute, up to 15 times.

Times in the brief use the laptop's clock style. The page's own clock is four-digit military time, such as `1805`.

## Where it goes

`config.json` holds `whatsapp_briefing_number` (digits only) or `whatsapp_briefing_invite` (a group's invite link). A group invite wins. Changes need a restart.

## Send a test

In a Terminal tab (PowerShell), from any folder. Type `curl.exe`, with the `.exe`. Plain `curl` is a different PowerShell command and it fails with "A parameter cannot be found that matches parameter name 'X'".

```powershell
curl.exe -X POST http://localhost:8340/wa/briefing/test
```

It answers `{"sent":true,"why":""}` when WhatsApp took it, or `sent` false with the reason. A test message has a "(test send)" line under the date. You can send one test a minute. It needs `whatsapp_enabled` to be `true`; otherwise it answers "WhatsApp is switched off." A test never uses up the day's brief.

On 2026-11-03 Rafiq ran the command above in PowerShell and it answered `{"sent":true,"why":""}`.

## Not tried yet

- The real 0700 send and the start-before-1100 catch-up.
- A day with real alerts, a weather warning or an event today.
- A send to a group.

If no brief comes, see **Problems and fixes**.
