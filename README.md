# Twitch Helper Generator

**Generate Twitch Pomodoro & Taskboard HTML overlays** with customizable colors and Twitch bot integration.  

---

## Overview

Twitch Helper Generator creates ready-to-use HTML overlays for OBS with:

- Pomodoro timer with task display  
- Taskboard with sidebar, task list, and completed task counters  
- Dark-themed, Twitch-style design with purple accents  
- Full color customization including transparency  
- Twitch bot credential integration (username, OAuth token, channel)  

---

## How to Use the Zip Release

1. **Download the zip** of the latest release.  
2. **Extract** it to any folder.  
3. Run **TwitchHelper.exe** (Windows).  
4. Enter your Twitch credentials:
   - **Bot Username**  
   - **OAuth Token** (starts with `oauth:`)  
   - **Channel Name**  
5. Adjust colors for Pomodoro and Taskboard overlays, including optional transparency.  
6. Click **Generate Pomodoro HTML** or **Generate Taskboard HTML**.
7. Add the `.html` file as a **Browser Source** in OBS.

---

## Twitch Bot Setup

1. Go to the [Twitch Token Generator](https://twitchtokengenerator.com/).  
2. Select **Bot Chat Token**.  
3. Log in with the Twitch account you want the bot to use.  
4. Generate the **Access Token** and copy it.  
5. Paste the token into the **OAuth Token** field in the generator.  
   - If it doesn’t start with `oauth:`, it will automatically be prefixed.  

> ⚠️ Keep your OAuth token secret. Do not share it publicly.  

---

## Feedback & Support

Encounter a problem or have suggestions? Use the **GitHub Issues** page to report bugs, request features, or ask questions:  

[Submit an Issue](https://github.com/AmadeusSpeaks/Taskboard-and-Pomodoro-Timer-Generator/issues)

When submitting an issue, include:

- Steps to reproduce the problem  
- Screenshots or error messages (if applicable)  
- Your operating system and version  
- Any other relevant details  

> ⚠️ Please do not share your OAuth token or other sensitive credentials in issues.

---

## Twitch Commands – Pomodoro Timer

> **Note:** Only moderators or the broadcaster can use these commands.

| Command                                       | Usage                                | Description                                                                                                      |
| --------------------------------------------- | ------------------------------------ | ---------------------------------------------------------------------------------------------------------------- |
| `!pomogoal {number}`                          | `!pomogoal 5`                        | Sets the Pomodoro goal (number of sessions to complete).                                                         |
| `!pomostart {pomoMinutes} {breakMinutes}`     | `!pomostart 25 5`                    | Starts the Pomodoro timer with the specified Pomodoro and break lengths in minutes. Resets current session to 1. |
| `!resetpomo`                                  | `!resetpomo`                         | Resets the Pomodoro timer to default settings (25 min Pomodoro, 5 min break, current session = 1).               |
| `!pause`                                      | `!pause`                             | Pauses the current Pomodoro timer.                                                                               |
| `!resume`                                     | `!resume`                            | Resumes a paused Pomodoro timer.                                                                                 |
| `!clearstorage`                               | `!clearstorage`                      | Clears all Pomodoro settings and progress stored in local storage and resets the timer.                          |
| `!pomogo {pomoMinutes} {breakMinutes} {goal}` | `!pomogo 25 5 5` or `!pomogo 25 5 ?` | Updates Pomodoro timer with specific Pomodoro length, break length, and goal. Use `?` for unlimited sessions.    |

**Notes:**

* `{number}` refers to an integer.
* `{pomoMinutes}` and `{breakMinutes}` are in minutes.
* `{goal}` is either a number of Pomodoros to complete or `?` for unlimited sessions.
* If you enter an invalid format, the bot will return usage instructions.

---

## Twitch Commands – Taskboard

> **Note:** Some commands are user-specific; others require moderator or broadcaster permissions.

| Command                       | Usage                           | Description                                                                                                 |
| ----------------------------- | ------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| `!add {task1}, {task2}, ...`  | `!add Do homework, Clean desk`  | Adds one or more tasks to your personal task list (comma-separated, max 15 tasks).                          |
| `!task {task1}, {task2}, ...` | `!task Buy groceries, Exercise` | Alias for `!add`. Adds tasks to your personal task list.                                                    |
| `!remove {taskNumber}`        | `!remove 2`                     | Removes a specific task from your list by its number.                                                       |
| `!done {taskNumber(s)}`       | `!done 1 3`                     | Marks one or multiple tasks as finished. If no number is provided, marks the first unfinished task as done. |
| `!start {taskNumber}`         | `!start 1`                      | Sets a specific task as the “current task” you are working on. Only unfinished tasks can be set.            |
| `!clear`                      | `!clear`                        | Removes all finished tasks from your personal task list.                                                    |
| `!clearalldone`               | `!clearalldone`                 | **Moderator/Broadcaster only.** Removes all finished tasks for all users.                                   |

**Notes:**

* Task numbers are **1-based** (the first task is `1`).
* Each user has their **own task list**; commands affect only the issuing user unless mod/broadcaster commands are used.
* You can add multiple tasks at once by separating them with commas.
* Finished tasks are tracked and can be removed individually (`!done`) or in bulk (`!clear` or `!clearalldone`).

---

## Included Files

- `TwitchHelper.exe` – The Electron app  
- `templates/pomodoro.html` – Pomodoro overlay template  
- `templates/taskboard.html` – Taskboard overlay template  
- `JainiPurva-Regular.ttf` – Font used in overlays  
- `tmi.js` – Twitch chat integration library  
- `renderer.js` & `main.js` – Electron source scripts  

---

## What is a Twitch Bot?

A **Twitch bot** is an automated account that can perform actions in your Twitch chat, such as posting messages, responding to commands, or interacting with overlays like the Pomodoro timer and Taskboard.  

In this app, the bot is used to send and receive chat messages from your Twitch channel so the generated overlays can reflect real-time tasks or timer events.  

---

## Creating a Twitch Bot Account

If you don’t already have a separate bot account, follow these steps:

1. Go to [Twitch.tv](https://www.twitch.tv/) and create a **new account** specifically for the bot.  
   - This keeps your main channel account separate from the bot, improving security.  
2. Choose a username for your bot (e.g., `MyChannelBot`).  
3. Verify the account via email.  
4. Once the account is ready, use the [Twitch Token Generator](https://twitchtokengenerator.com/) to generate a **Bot Chat Token** for this bot account.  
5. Paste the token into the **OAuth Token** field in the app.  

> ⚠️ Never use your main Twitch account as a bot. Always create a dedicated bot account to keep credentials safe and prevent accidental bans.
> 
---

## License

All Rights Reserved © 2025 DarkwireStudios  

Do not copy, modify, redistribute, or use this software without explicit written permission.
