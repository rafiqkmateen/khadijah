# Start here

Purpose: walk you from a switched-off laptop program to asking Khadijah a question, and then shutting her down.
Owner: Rafiq. Version 0.5.1 (0.5.1: the restart button reads RESTART KHADIJAH; the picture of the box is unchanged, not yet agreed, 2026-11-16; 0.5.0: written for The City, her new home screen: the opening title, her written answer line, the event line, the restart steps and new pictures, 2026-11-16; 0.4.0: agreed by Rafiq, 2026-11-04; Escape now says it stops her reply, and the restart wait is about ten seconds; 0.2.0 was agreed by Rafiq, 2026-11-02). Date: 2026-11-16.

Do these steps in order the first time. It takes about five minutes.

## Before you start

- Khadijah now uses the older assistant's ports, so the two cannot run at the same time. If the older assistant is running, close it first.
- Your AI key must be saved. If it is not, she will tell you when she starts. The page "Add, change or remove a key" shows how.

## 1. Start her

1. Open the Khadijah folder, `C:\Users\you\projects\khadijah`.
2. Double-click `start-assistant.bat`.

A black window may flash up for a few seconds and go down again. That means the start worked. Her working rooms (the server and the file watcher) run out of sight, so there is nothing to leave open. After a short wait, Chrome opens her page at `http://localhost:8340`.

**What you should see:** her screen, **The City**. First a short title shows her name and "His city, from his own drone" over the picture. When her server is ready, the title fades and you see Home: Philadelphia, with the menu on the left and her card names on the picture. Her pill in the upper right corner says STANDBY and MIC OFF. A click or any key skips the title.

**If it does not:** open the server log, `logs\assistant_server.log` in her folder. It says what went wrong. Then read **Problems and fixes**.

## 2. Wait until she is ready

Give her about a minute. Her voice needs time to load. If you ask a question too early, her answer may be silent, and her pill may say "VOICE NOT READY".

## 3. Ask a question

1. Click the message box at the bottom of the page.
2. Type a question, for example: `What is two plus two?`
3. Press Enter.

**What you should see:** "You:" and your question in the event line at the lower left. Her pill says THINKING, then TALKING. Her answer is written just above the message box. **What you should hear:** her answer, spoken, for example "Two plus two is four, sir."


If you hear nothing, check the speaker button in the message bar. It turns her voice on and off. If it is on and you still hear nothing, her voice is not ready yet.

## 4. Look around

- The **menu** on the left opens Home, her eight places, and Calendar, Tasks and WhatsApp.
- The **strip** across the top shows the laptop's load, memory, graphics and temperature, then the date and clock.
- **Her pill** in the upper right corner shows her face, her name, what she is doing and which AI is answering.
- The **event line** at the lower left lists the newest things that happened.
- The **message bar** at the bottom has the Mic button, the message box, the speaker button and the Send arrow. **RESTART KHADIJAH** and **STOP KHADIJAH** sit beside it.

**What you see on the screen** explains each part.

Two keys are worth knowing:

- **M** or **Space** turns the microphone on and off. It is off every time the page opens.
- **Escape** stops her reply, and closes an open card.

## 5. Stop her

1. Click **STOP KHADIJAH**, right of the message bar.
2. A box asks "STOP KHADIJAH?". Click **OK**.

The button says "Shutting down…". Her page stops working and her programs end. This is the normal way to shut her down.

## 6. Restart her

1. Click **RESTART KHADIJAH**, right of the message bar.
2. A box asks "RESTART KHADIJAH?". Click **OK**.


The button says "Restarting…". The old tab dims. It closes if it is the tab her start-up opened; any other tab goes blank, and you can close it. After about ten seconds she starts again, and her page opens again by itself. The new page always loads fresh, with the opening title.


If her start file is missing, the restart does not start. A box says so, and nothing is stopped.

You can also type "stop Khadijah" or "restart Khadijah" in the message box and press Enter. These two act at once, with no box asking you to confirm.

## Where to go next

- **Problems and fixes** if a step did not work.
- The contents page for everything else.
