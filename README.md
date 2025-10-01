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

# Twitch Command List

## Pomodoro Timer Commands

> Commands for controlling the Pomodoro timer. Restricted to moderators or broadcaster.

| Command         | Usage                                         | Description                                                           |
| --------------- | --------------------------------------------- | --------------------------------------------------------------------- |
| `!pomogoal`     | `!pomogoal {number}`                          | Set the Pomodoro goal (number of Pomodoros).                          |
| `!pomostart`    | `!pomostart {pomoMinutes} {breakMinutes}`     | Start a Pomodoro timer with specified work and break durations.       |
| `!pomogo`       | `!pomogo {pomoMinutes} {breakMinutes} {goal}` | Start a Pomodoro with custom goal. Use `?` for unlimited goal.        |
| `!resetpomo`    | `!resetpomo`                                  | Reset Pomodoro timer to default settings (25 min work / 5 min break). |
| `!pause`        | `!pause`                                      | Pause the Pomodoro timer.                                             |
| `!resume`       | `!resume`                                     | Resume the Pomodoro timer.                                            |
| `!clearstorage` | `!clearstorage`                               | Clear saved Pomodoro settings and reset timer.                        |

---

## Taskboard – User Commands

> Commands any viewer can use for managing their personal tasks.

| Command   | Usage                              | Description                                                                                  |
| --------- | ---------------------------------- | -------------------------------------------------------------------------------------------- |
| `!add`    | `!add Task 1, Task 2`              | Add new tasks (up to 15 at once).                                                            |
| `!task`   | `!task Task 1, Task 2`             | Alias for `!add`.                                                                            |
| `!remove` | `!remove {taskNumber}`             | Remove a specific task by its number.                                                        |
| `!done`   | `!done {taskNumber(s)}`            | Mark one or multiple tasks as finished. Omitting the number marks the first unfinished task. |
| `!start`  | `!start {taskNumber}`              | Mark a task as “current” to show it prominently on the taskboard.                            |
| `!clear`  | `!clear`                           | Remove all finished tasks from your list.                                                    |
| `!edit`   | `!edit {taskNumber} {newTaskText}` | Edit the text of a specific task.                                                            |
| `!check`  | `!check`                           | List your unfinished tasks with their numbers.                                               |
| `!tbhelp` | `!tbhelp`                          | Show a list of all **user** Taskboard commands.                                              |

---

## Taskboard – Moderator / Broadcaster Commands

> Commands restricted to moderators and the channel broadcaster. Affect multiple users.

| Command           | Usage                                     | Description                                                      |
| ----------------- | ----------------------------------------- | ---------------------------------------------------------------- |
| `!clearalldone`   | `!clearalldone`                           | Remove all finished tasks for everyone.                          |
| `!clearalltasks`  | `!clearalltasks`                          | Clear **all tasks** for every user.                              |
| `!cleartasksuser` | `!cleartasksuser {username}`              | Clear all tasks for a specific user.                             |
| `!removetaskuser` | `!removetaskuser {username} {taskNumber}` | Remove a specific task from another user.                        |
| `!tbhelpmod`      | `!tbhelpmod`                              | Show a list of all **moderator/broadcaster** Taskboard commands. |

---

### Notes

* Users can only modify **their own tasks**.
* Moderators and broadcasters can manage **all users’ tasks**.
* Commands are **case-insensitive**.
* For multiple tasks in `!add` or `!task`, separate with commas.
* Task indices start at `1`.

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
