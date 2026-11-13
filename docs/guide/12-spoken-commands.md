# Spoken commands

Purpose: show you the short phrases she answers at once, without thinking, and what to do when one does not work.
Owner: Rafiq. Version 0.4.1 (0.4.1: the count also names each group, 2026-11-12; 0.4.0: the feature-count phrase, 2026-11-12; 0.3.0: three new phrases, 2026-11-09; 0.2.0: agreed by Rafiq 2026-11-03, with a line added for the missing Anthropic key; 0.1.3: she names five or six things, a different handful each time, CL-048, 2026-11-03). Date: 2026-11-03.

A few phrases are answered right away. She does not ask the AI for these, so they are fast and they cost nothing. You can say them with the microphone or type them in the message box. Typing works the same.

Her answers are spoken. The page does not write them out. To see what she did, watch the screen change, or watch the list of events above the message box.

## Before you start

- For the "open" commands, the setting `nodes` in `data\config.json` must be `true`, and so must the groups under `features`. On this laptop they are. See **Settings you can change**.
- You may start with "please", or with "can you", "could you" or "would you". You may end with "for me", "please" or "now".

## The phrases

| Say | What she does |
|---|---|
| "switch to Sonnet", "switch to Haiku" or "switch to Gemini" | Changes the AI she uses. She says "Switched to Sonnet." and so on. Gemini needs its own key. |
| "which model" | Tells you which AI is in use, and whether automatic switching is on. |
| "model routing on" or "model routing off" | Turns the automatic move to Sonnet for hard questions on or off. |
| "which version" | Tells you her version number. |
| "how many features do you have" | Tells you how many features she has, then how many are in each group, counted from the list of everything she can do. |
| "remember that ..." | Saves a note. See **Your notes**. |
| "open Calendar", "go to Tasks", "show me WhatsApp" | Opens that part of the menu. She says "Opening Calendar." |
| "open Network Mapper" | Goes to the group that holds it and opens its card. |
| "reverse engineer" and a website address, program or app name | Reads it with the Reverse Engineer. See **The machine and creative parts**. |
| "flush system resources", then "go" | Lists what she would close, then closes it after you say go and press Yes when Windows asks. |
| "restart Claude", then "go" | Asks first, then closes every Claude window and opens the app again. |
| "rotate the satellites" | On Home, every picture swings around its ring and settles. On other screens nothing moves. |
| "open Claude" | Opens the Claude website in your browser. "open Anthropic console" opens the console. |
| "add task buy milk" | Adds a task. |
| "change task 2 to buy bread" | Changes task number 2. |
| "delete task 2" | Deletes it. She says "Say undo that to bring it back." |
| "undo that" | Brings back the task you deleted, if it was in the last 10 minutes. |

You can name a task by its number, as the Tasks screen counts them from 1, or by some of its words. Calendar events in the list are not counted.

Say "can you add a task" and she asks "What is the task?". The next thing you say is the answer. Say "cancel" or "never mind" to drop the question. She forgets an unanswered question after two minutes.

## Asking your calendar

Ask in your own words, for example "what is on my calendar this week". This one is not instant. She asks the AI to read your real calendar, then tells you what it found. It needs the calendar address. See **Add, change or remove a key**.

## Asking what she can do

Say or type "what can you do". This one is not instant either. She asks the AI, which names five or six things she can do, a different handful each time, and says there is much more. She does not search the web for it.

## When she is not sure what you meant

If you say a node's name a little wrong, she opens it. If the name is too far off to open, but close to one node, she asks "Did you mean Network Mapper?". You can answer:

- "yes", when she named one node.
- The name, or part of it.
- "the second one" or "the last one", when she named more than one.
- "no" or "never mind". She says "Understood" and drops it.

She waits two minutes for your answer. After that, your next words are a normal message.

## What you should see

- She speaks the answer at once. There is no pause where she is thinking.
- The list of events above the message box shows what you said ("You: ..."). After a task command it also says "Tasks updated".
- The server log shows your words, then a line that says `Model: none (Python reply)`. That line means no AI was asked.

## Tried on 2026-11-02

In a real Chrome, with the typed box: which model, switch to Sonnet and Haiku, open Calendar, open Home, open a node by name, "Did you mean" answered yes and no, rotate the satellites, add, change, delete and undo a task, and a calendar question with the real key. Each one showed `Model: none (Python reply)` in The server log, except the calendar question, which asked the AI as it should. The task file was put back exactly as it was. **Not tried:** saying them aloud into the microphone, and the film of the satellites moving.

## If it did not work

- **She answered with the AI instead** (a reply that says she can only open a website). The words were not matched. Read the server log's line that starts with `Heard:` to see what she heard. Check that `nodes` is `true` in `data\config.json` and restart her.
- **"Only Haiku, Sonnet and Gemini are available."** You named another AI.
- **"Claude is not set up yet. It needs an Anthropic key."** You asked for Sonnet or Haiku and no Anthropic key is saved. Save one. See **Add, change or remove a key**.
- **"Gemini is not set up yet."** Save a Gemini key. See **Add, change or remove a key**.
- **"Tasks are switched off."** The tasks folder is not set. See **Tasks and calendar**.

More help is in **Problems and fixes**.
