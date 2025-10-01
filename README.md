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

## Included Files

- `TwitchHelper.exe` – The Electron app  
- `templates/pomodoro.html` – Pomodoro overlay template  
- `templates/taskboard.html` – Taskboard overlay template  
- `JainiPurva-Regular.ttf` – Font used in overlays  
- `tmi.js` – Twitch chat integration library  
- `renderer.js` & `main.js` – Electron source scripts  

---

## License

All Rights Reserved © 2025 DarkwireStudios  

Do not copy, modify, redistribute, or use this software without explicit written permission.
