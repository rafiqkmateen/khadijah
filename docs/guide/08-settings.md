# Settings you can change

Purpose: list the settings you may change by hand, in plain words, and say where.
Owner: Rafiq. Version 0.4.1 (0.4.1: `face_live_root` is empty on this laptop, 2026-11-05; 0.4.0: agreed by Rafiq, 2026-11-04; no words changed; 0.3.2: the F5 voice is gone, 2026-11-03; 0.3.1: 0.1.0 was agreed by Rafiq, 2026-11-02; "Opening things by voice" and the corrections of 2026-11-02 were added after, not yet agreed). Date: 2026-11-05.

Almost every setting you may want is in one file: `data\config.json`. Open it in Notepad. Never paste it anywhere, because it holds private details.

Keys and passwords are not in this file. Read **Add, change or remove a key** for those.

A change takes effect after you restart Khadijah.

## About you

| Setting | What it does | Example |
|---|---|---|
| `user_name` | The name she uses for you. Without it she says "the user". | `"Rafiq"` |
| `user_address` | How she addresses you at the end of a spoken line. Without it she uses none. | `"sir"` |
| `user_role` | What you do. She adds it to her instructions. | |
| `user_about` | A few words about you, in your own words. Up to 500 letters. | |
| `user_languages` | Your languages. She answers in the language of your last message either way. | |
| `user_units` | `"metric"` or `"imperial"`. Without it, she uses the custom of your country, and that needs your country set in `location` (`country_code`, such as `"US"`). With no country she uses metric. | |

## Her voice and ears

| Setting | What it does |
|---|---|
| `voice_engine` | Which voice speaks. `"omni"` is her own voice, made on this laptop. This is the one in use. `"elevenlabs"` is an online voice and needs its own key. A name she does not know, including the old `"f5"`, becomes `"omni"` without a warning. |
| `mic_whisper` | Set to `false` to turn off turning your speech into words. |
| `whisper_model` | Which listening model to use. The default is `"small"`. |

## Times and dates

`time_style` and `date_order`. See **Change how times and dates are written**.

## Her face

| Setting | What it does |
|---|---|
| `face_live` | Set to `false` to stop her mouth following her words. It is off on this laptop for now. |
| `face_live_root` | Where the face software is. It is empty on this laptop, because her live mouth is off. If you install the face software, put its folder here. |

## Opening things by voice

| Setting | What it does |
|---|---|
| `nodes` | Set to `true` so she can open a node by name ("open Network Mapper"). With `false` she opens none, and says she can only open the Claude and Anthropic console websites (her wording varies). It is `true` on this laptop. |
| `features` | One switch for each group of nodes, such as `system` or `money`. A node answers to its name only when its group is `true`. All are `true` on this laptop. |

See **Spoken commands**.

## Your tasks

`obsidian_inbox_path` names the folder that holds `Tasks.md`. For this project it is the `user-tasks` folder.

## Settings you should leave alone

Many other values, such as time limits and the list of words that make a question "hard", are in the file `settings.py`. They are for builders. The Developer Guide lists them all.

## If a change did nothing

- You did not restart her. Restart her.
- The file has a typing mistake. A missing quote mark or comma stops her from starting. The server log says "Setup is not finished" and names the line. Fix it and start her again.
- A value is the wrong kind. For most of the settings above she prints a warning in the server log and uses the usual value. For `time_style`, `date_order`, `voice_engine`, `mic_whisper`, `whisper_model`, `face_live` and `face_live_root` she says nothing and uses the usual value, so check your spelling.
