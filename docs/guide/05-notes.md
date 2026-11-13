# Your notes

Purpose: show you how to save a note and how she uses your notes.
Owner: Rafiq. Version 0.1.2 (0.1.2: the brief time is military time and its notes are the saved ones, 2026-11-05; 0.1.1: agreed by Rafiq, 2026-11-02). Date: 2026-11-05.

Notes are plain text files on this laptop. They are in the `data\notes` folder inside the Khadijah folder.

## Save a note

1. Click the message box.
2. Type `remember that` and then what you want to keep. For example: `remember that the plumber comes on Friday`.
3. Press Enter.

**What you should see:** she answers "Noted:" and the title of the note. The note is a new file in `data\notes\captures`. No AI is used for this step.

How the note is named: today's date and the first six words. If that name is already used, she adds -2, -3 and so on. She never replaces an old note.

A note is cut off at 2000 letters.

If you type `remember that` and nothing else, she asks "Remember what?" and adds your form of address, for example "Remember what, sir?"

## Ask about your notes

Ask a question that sounds like it is about your notes. For example: `What did I write about the plumber?`

She looks for the five notes that match best. She reads the start of each one, and uses them to answer that one question. She does not follow any instructions written inside a note.

She does not use your notes when your message is short and contains her wake phrase ("Hey Khadijah" or "activate").

## Where the notes are

| Folder | What is in it |
|---|---|
| `data\notes` | Your own notes |
| `data\notes\captures` | Notes saved with "remember that" |
| `data\notes\teardowns` | Page teardowns. These come from the Teardown tool (see **The machine and creative parts**). |

A file bigger than 200 KB is ignored.

## What you cannot do yet

The 0700 morning brief includes your newest saved notes (the ones in `captures`), up to two from the last seven days. It arrives as a WhatsApp message and is not read aloud (see **Morning brief**).
