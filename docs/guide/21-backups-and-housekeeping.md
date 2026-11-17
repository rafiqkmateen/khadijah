# Backups and housekeeping

Purpose: show you how to back up the project, and how to watch the laptop for the random reboots.
Owner: Rafiq. Version 0.7.0 (the section on taking her off the laptop, with the full uninstaller, CL-190, 2026-11-15; 0.6.1: earlier-app wording removed, 2026-11-12; 0.6.0: every backup pauses the WhatsApp bridge and the weekly task moves to 0900, CL-079, 2026-11-08; 0.5.0: the Desktop shortcut and the weekly backup, the git checks, 2026-11-04; 0.4.1: the Windows warning is recorded as seen, from Rafiq's word in the 2026-11-03 morning session; 0.4.0: agreed by Rafiq 2026-11-03, with the revert-lines answer corrected, the watcher status updated and the code boxes tagged powershell; 0.3.0: the file watcher section added by CL-045, 2026-11-03; Missions left out of the zip, 2026-11-03). Date: 2026-11-15.

Two small tools sit beside her. Neither one needs her to be running. Both are safe to run at any time.

## Back up the project

This makes one zip of the whole project and keeps the newest five.

1. See what it would do first. It changes nothing:

   ```powershell
   powershell -NoProfile -ExecutionPolicy Bypass -File C:\Users\you\projects\khadijah\scripts\powershell\khadijah_maintenance.ps1 -WhatIf
   ```

2. Run it for real by leaving off `-WhatIf`.

**What you should see:** a line such as "packed 1,667 files, 28.7 MB of files into 26.0 MB", and the zip in `Desktop\khadijah_backups`. The zip is named `khadijah_` and the date and time.

- It leaves out `.git`, `.venv`, `.venv-voice`, `whisper-models`, `.cache`, `node_modules`, `__pycache__`, `backup`, `_backups`, `logs`, `.claude` and `Missions`, and any `.zip`, `.pyc` or `.tmp` file. Most rebuild, but `logs` and `.claude` do not, so they are not in the zip. `Missions` holds your moved drone footage, which is large and exists nowhere else. It is not in the zip, so copy that folder yourself if you want it kept safe. Your mission list, `data\missions.json`, is in the zip.
- It also thins the per-file `.bak_` copies in `backup` and `frontend\backup`, sending the old ones to the Recycle Bin. Add `-SkipTidy` to skip that.
- Before it copies anything it asks her server to close the WhatsApp bridge, and when the zip is done it asks the server to start it again, even if the backup failed. It prints how many seconds the bridge was down (about 20). A killed bridge would be restarted by her within seconds, so the server does the pausing; if the tool dies in the middle, she brings the bridge back by herself after five minutes. If she is not running, the tool says so and backs up anyway. Any other file she is holding open is reported and left out.
- It never touches any folder outside Khadijah's own.
- Nothing is ever erased for good. Anything it removes goes to the Recycle Bin.
- Add `-IncludeScreenshots` to also send your Screenshots folder to the Recycle Bin. It is off unless you ask.

## The one-click backup and the weekly backup

Two things were set up on 2026-11-04. Both make the same zip as above, and neither thins old copies.

1. A Desktop shortcut called **Back Up Khadijah**. Double-click it. It makes one zip in `Desktop\khadijah_backups`, then waits for you to press a key.
2. A Windows task called **Khadijah weekly backup**. It runs every Sunday at 0900 (moved from 0300 on 2026-11-08, because the laptop is not on at 0300). If the laptop was off then, it runs the next time the laptop is on. It runs only while you are signed in. The first one is Sunday 2026-11-08: look in `khadijah_backups` for a new zip.

The `sources` folder (her face photo) is in the zip. The `Missions` folder is not. A copy of your drone clip is on drive Z, in `Khadijah backups\Test flight 12 Sep`.

## Taking her off the laptop

Khadijah is one folder, plus three things Windows runs on its own outside it: the task **Khadijah weekly backup** (Sundays at 0900), the task **Khadijah health check** (every second day at 0500; a tool for working on her with Claude Code, and before 2026-11-15 it ran weekly) and the Desktop shortcut **Back Up Khadijah**. Deleting the folder alone leaves the two tasks behind, failing every time. One script takes her off properly, in this order: it stops her, makes one last backup zip, removes the two tasks, the health check's start-up note for Claude and the shortcut, and, only if you ask, sends her folder to the Recycle Bin.

1. See what it would do (changes nothing):

```
powershell -NoProfile -ExecutionPolicy Bypass -File "C:\Users\you\projects\khadijah\scripts\powershell\uninstall_khadijah.ps1"
```

2. Remove her tasks and shortcut, keep her folder: add `-Go` to that line.
3. Remove everything: add `-Go -RemoveFolder`. It asks you to type the word REMOVE, then sends her whole folder to the Recycle Bin (never a hard delete, so you can still put it back). It refuses any folder that does not hold `start-assistant.bat`. Before it moves anything it checks two more things and refuses, touching nothing of her folder, if either fails: her folder must fit in the Recycle Bin (Windows would otherwise delete a folder that is too big for the bin for good, without asking; the dry run with `-RemoveFolder` shows her folder's size and what the bin can hold), and none of her programs may still be running from her folder (it names them; close them or restart the laptop and run it again).

**What you should see:** a numbered list of the four steps; with `-Go`, a line for each thing removed, "Last backup made.", and at the end "Done." The backup zips stay in `Desktop\khadijah_backups`; the script never touches them. If she does not stop within 30 seconds, or the backup fails, nothing is removed. The last backup cannot be skipped when her real folder is to go. To remove only the tasks and shortcut without the stop and the backup, run `scripts\powershell\uninstall_scheduled_tools.ps1` (it also has `-WhatIf`).

## Watch for the random reboots

The heartbeat logger writes a line every few seconds to the `logs` folder, so after a freeze the last line shows what the laptop was doing. It only reads.

- See one reading now:

  ```powershell
  cd C:\Users\you\projects\khadijah; .venv\Scripts\python.exe scripts\python\heartbeat_logger.py --once
  ```

- To keep it running with no window, start it with `pythonw` instead of `--once`. A START line with no STOP line before it means the last run ended without warning.

To test whether power saving causes the reboots, a second tool turns three power-saving features off. It changes Windows settings, so only you run it, and only in an administrator window.

1. Right-click PowerShell and choose **Run as administrator**.
2. Run this:

   ```powershell
   powershell -File C:\Users\you\projects\khadijah\scripts\powershell\reboot_test_settings.ps1
   ```

3. It saves the old values to `logs\reboot_test_settings_before.txt` first. It then turns off Fast Startup, USB selective suspend and the Bluetooth adapter's power saving. It shows BEFORE and AFTER.
4. To put them back, run the same line with `-Revert` added.
5. In a window that is not an administrator, it says "Not an administrator window" and changes nothing.

Fast Startup changes only at your next shutdown.

## Check that she is working

The preflight check asks the running app eight real questions. It makes a real call to the AI, saves one test note and deletes it, and checks that `config.json` cannot be fetched from a browser. Start her first, then run:

```powershell
C:\Users\you\projects\khadijah\.venv\Scripts\python.exe C:\Users\you\projects\khadijah\util\preflight.py
```

It ends with a line such as "11 pass, 0 fail, 0 warn." While it runs it takes over the live page for a moment, so reload your page after it.

## The file watcher

The file watcher is a small program that guards your files. It starts by itself, out of sight, when you start her. It looks at every file in her folder every 20 seconds and writes one line to a log for each file that was made, changed or deleted.

It has one special job. If a file goes back to what it held a little while ago, the watcher writes a line with `!!! REVERT DETECTED !!!`, shows a Windows warning and beeps. That is how you catch a saved change that quietly disappears.

It skips the places that change all day and tell you nothing: backups, caches, the voice program, the speech models, her WhatsApp login, the Chrome profile and her logs.

Stop closes its window. When it starts again, it says what changed while it was off.

**Read the end of the log.** This works from any folder:

```powershell
Get-Content C:\Users\you\projects\khadijah\data\tripwire\file_revert_watch_log.txt -Tail 20
```

**Find every revert it has caught.** It may print lines. Most are the test program's cache file (`.pytest_cache`), which flips back whenever tests run, and mean nothing. A line for one of your own files is worth a look:

```powershell
Select-String -Path C:\Users\you\projects\khadijah\data\tripwire\file_revert_watch_log.txt -SimpleMatch 'REVERT DETECTED'
```

**Check it is alive.** It writes a line that says `watcher alive` every 15 minutes. The newest one should be less than 15 minutes old.

## Not set up yet

- The git checks are part of the project now. Every commit runs the document check and the code check, and a commit with a problem is refused. After a fresh copy of the project, run `.venv\Scripts\python.exe scripts\python\git_hook_checks.py install` once.
- The file watcher was tried in tests and in one real pass over the project. It has run in its own window from the start script, three times on 2026-11-03. Rafiq saw its Windows warning appear as a window on 2026-11-03 (his word). Its beep was not confirmed.
- A real heartbeat run in the background was not started.
- The reboot settings script was run only from an ordinary window, where it refused. It has not been run as an administrator.

If a tool does not run, see **Problems and fixes**.
