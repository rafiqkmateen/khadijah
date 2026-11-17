# Tasks and calendar

Purpose: show you how to keep your task list and read your calendar.
Owner: Rafiq. Version 0.7.1 (0.7.1: the card names an other calendar it could not read, not yet agreed, 2026-11-16; 0.7.0: she also reads your other Google calendars, read only, and a calendar shared only as free or busy shows as Busy, CL-207, not yet agreed, 2026-11-16; 0.6.0: Tasks and Calendar are The City's own cards: where they open, what they show, a tick saved first, new pictures, 2026-11-16; 0.5.0: agreed by Rafiq, 2026-11-04; the seven days and six events were checked in the code; no words changed; 2026-11-03: a task may be 400 letters, CL-047, not yet agreed; 2026-11-03: reading tasks aloud added, not yet agreed; 2026-11-03: dates up to a year added, not yet agreed; pictures added 2026-11-02, not yet agreed; 0.1.0 was agreed by Rafiq, 2026-11-02; the calendar key part and the spoken part were added after, not yet agreed). Date: 2026-11-16.

## Your tasks

Your tasks live in one plain text file called `Tasks.md`. For this project it is in the `user-tasks` folder inside the Khadijah folder. Each open task is a line that starts with `- [ ]`.

Only Khadijah's own page on this laptop can change it.

### Add a task

1. Click **Tasks** in the menu. The Tasks card opens as a wide list in the middle of the screen, over a still picture of the open sea.
2. Click the box that says "Add a task" at the bottom of the card.
3. Type the task and press Enter, or click **Add**.

**What you should see:** the task appears in the list, and the number in the title goes up.


A task longer than 400 letters is cut off at 400.

### Tick a task off

Click the tick box beside the task, or click the task's words.

**What you should see:** once the change is saved, the task is struck through, then leaves the list. In the file, it is now marked done. If the save fails, the task stays as it was and the card says why on its bottom line.

Calendar events in the list cannot be ticked. They are only there to show you what is coming.

### Change a task

1. Click the pencil mark beside the task.
2. Change the words and press Enter. Press Escape to cancel.

### Delete a task

Click the X beside the task.

**Made a mistake?** A bar under the list says "Deleted:" and the task. Click **Undo** within 10 seconds. The task comes back in its old place.

### When there are no tasks

The list says "No open tasks." The calendar items still show under it.

### By voice

You can also say "add task buy milk", "change task 2 to buy bread" and "delete task 2". "Undo that" brings back a task you deleted in the last 10 minutes. Say "read my tasks" or "what are my tasks" and she reads your open tasks aloud; she lists them only when you ask. The steps are in **Spoken commands**.

## Your calendar

Khadijah reads your Google Calendar. The events show in two places:

- The **Tasks** screen lists up to six events from the next seven days, each with a small calendar mark.
- The **Calendar** screen shows the whole month.

### Read the calendar

1. Click **Calendar** in the menu. The Calendar card fills the screen beside the menu, over a still picture of the Ben Franklin Bridge seen from above.
2. Use the arrows to change month. Click **Today** to come back. **Refresh** reads your calendar again.

**What you should see:** the month, with each day's events written in its box (up to two; when a day has three or more, one event and then "+N more"). Today is marked, and past events are dimmed. Beside the month, "Coming up" lists the next events. Click "+N more" to see all of that day's events there. Clicking a day's number starts a new event on that day, when the calendar can be changed.


If your calendar cannot be read, the card says "The calendar could not be loaded." It tries again by itself every five minutes. If only one of your other calendars cannot be read, the events of the rest still show and the line under the card says "Could not read:" and names that calendar.

### Your other calendars

Khadijah reads your own calendar and any other Google calendars you list in `config.json` under `google_calendar_extras`. She only reads them: nothing is ever added, changed or deleted on them. Each one is an id, or an id with a name, for example `{"id": "you@work.com", "name": "Resilient Core"}`; the name is what shows on the event. The calendar must be shared with her Google account first (Google Calendar, Settings, "Share with specific people").

If the calendar is shared only as free or busy, Google sends no titles, so each event shows as **Busy** with the calendar's name beside it. That is all she can show until the owner shares the details. Restart her after you change `config.json`. These events are read only on the Calendar screen, so the edit buttons do not appear on them.

### Change the calendar

Click an empty part of a day's box, and the New event form opens for that day. Click an event, and the Change event form opens. To delete an event, press **Delete**. It changes to "Press again to delete". Press it again.

This only works after you save a second key, the calendar's Google key, and share your calendar with it. The steps are in **Add, change or remove a key**. Until then the screen says "Google Calendar is not connected, so events can be read but not changed." and you change events in Google Calendar itself.

With your real key it has been tried on the screen: a test event was added, changed and deleted, and nothing was left in your calendar.

### Ask about your calendar by voice

Say or type "what is on my calendar this week". You can ask about any dates up to a year ahead, for example "next month" or "this weekend". She reads your real calendar and tells you the events. This only reads. Changing events is done on the Calendar screen. See **Spoken commands**.

### If the calendar is empty

Read **Problems and fixes**, the entry about the calendar.
