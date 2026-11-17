# Change how times and dates are written

Purpose: show you how she decides between 14:30 and 02:30 PM, and between day first and month first.
Owner: Rafiq. Version 0.3.0 (0.3.0: agreed by Rafiq, 2026-11-04; no words changed; 0.1.0 was agreed by Rafiq, 2026-11-02; the start-up line was corrected after, not yet agreed). Date: 2026-11-04.

By default she writes times and dates the way Windows does on this laptop. If you change Windows, she follows at once.

You can also tell her your own choice.

## Follow Windows

1. Open Windows **Settings**.
2. Go to **Time and language**, then **Language and region**, then **Regional format**.
3. Change the format.

Nothing else is needed.

## Choose your own

You set two choices in the file `data\config.json`. Do not paste that file anywhere.

| Setting | Choices |
|---|---|
| `time_style` | `"12"`, `"24"` or `"system"` (follow Windows). |
| `date_order` | `"mdy"` (month first), `"dmy"` (day first), `"ymd"` (year first) or `"system"`. |

1. Open `data\config.json` in Notepad.
2. Add or change the setting you want.
3. Save the file.
4. Restart Khadijah. She reads this file only when she starts.

**What you should see:**
- A time reads `14:30` on the 24-hour choice and `02:30 PM` on the 12-hour choice.
- A day reads "Wednesday, 28 October" day first, "Wednesday, October 28" month first, or "Wednesday, 2026 October 28" year first.

## If it did not work

- If `config.json` has a typing mistake when she starts, she does not start. The server log says "Setup is not finished" and names the line. Fix the mistake and start her again.
- If the file cannot be read after she has started, Windows decides. Nothing breaks.
- If Windows itself cannot be read, she uses the 12-hour clock with the month first.
