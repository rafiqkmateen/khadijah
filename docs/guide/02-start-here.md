# Start here

Purpose: walk you from a switched-off laptop program to asking Khadijah a question, and then shutting her down.
Owner: Rafiq. Version 0.4.0 (0.4.0: agreed by Rafiq, 2026-11-04; Escape now says it stops her reply, and the restart wait is about ten seconds; 2026-11-03: typed stop and restart added, not yet agreed; 0.2.0 was agreed by Rafiq, 2026-11-02; a picture of Home was added after, not yet agreed). Date: 2026-11-04.

Do these steps in order the first time. It takes about five minutes.

## Before you start

- Khadijah now uses the older assistant's ports, so the two cannot run at the same time. If the older assistant is running, close it first.
- Your AI key must be saved. If it is not, she will tell you when she starts. The page "Add, change or remove a key" shows how.

## 1. Start her

1. Open the Khadijah folder, `C:\Users\you\projects\khadijah`.
2. Double-click `start-assistant.bat`.

A black window may flash up for a few seconds and go down again. That means the start worked. Her working rooms (the server and the file watcher) run out of sight, so there is nothing to leave open. After a short wait, Chrome opens her page at `http://localhost:8340`.

**What you should see:** the page fades in one piece at a time. First the menu on the left, then the middle of the screen. This takes about five seconds.


**If it does not:** open the server log, `logs\assistant_server.log` in her folder. It says what went wrong. Then read **Problems and fixes**.

## 2. Wait until she is ready

Give her about a minute. Her voice needs time to load. If you ask a question too early, her answer may be silent, and the page may say "VOICE NOT READY".

## 3. Ask a question

1. Click the message box at the bottom of the page.
2. Type a question, for example: `What is two plus two?`
3. Press Enter.

**What you should see:** the line "You:" with your question appears in the event list above the message box. **What you should hear:** her answer, spoken, for example "Two plus two is four, sir." Her answers are spoken only. They are not written on the screen.

If you hear nothing, her voice is not ready. Read her answer in the server log (`logs\assistant_server.log`): look for the line that starts "LLM reply:".

## 4. Look around

- The **menu** on the left opens each part of her.
- The **strip** across the top shows the laptop's load, memory, graphics and temperature.
- The **right panel** shows her face, her name, and what she is doing.
- The **bottom bar** has the message box, and the Stop, Restart and microphone buttons.

Three keys are worth knowing:

- **M** turns the microphone on and off. It is off every time the page opens.
- **G** switches her between a face and a glowing sphere.
- **Escape** stops her reply.

## 5. Stop her

1. Click **STOP KHADIJAH** in the bottom bar.
2. A box asks "STOP KHADIJAH?". Confirm it.

Her page stops working and her programs end. This is the normal way to shut her down.

To start fresh, click **Restart** instead. Click OK in the box that asks RESTART KHADIJAH?. The old tab closes, and after about ten seconds she starts again and a new Chrome tab opens by itself.

You can also type "stop Khadijah" or "restart Khadijah" in the message box and press Enter. These two act at once, with no box asking you to confirm.

## Where to go next

- **Problems and fixes** if a step did not work.
- The contents page for everything else.
