# GameHub v1.0.0 (Public Tester Release) 🎮

A native macOS gaming launcher designed to give your Mac a sleek, console-inspired (PlayStation 5 style) dashboard for Windows games running via CrossOver.

---

## ⚠️ Important Testing Disclaimer
> **Please Note:** Game launching and individual game compatibility **have not been verified** in this release build. To strictly preserve testing environments, no actual game executables were launched or run during automated release checks. GameHub provides the launch commands, process monitors, and controller environment hooks, but your actual gameplay performance will depend on your CrossOver and Wine configuration.

---

## System Requirements
- **Operating System:** macOS 13.0 (Ventura), macOS 14.0 (Sonoma), or macOS 15.0+ (Sequoia).
- **Architecture:** Universal 2 binary — runs natively on both **Apple Silicon** (M1/M2/M3/M4) and **Intel** Macs.
- **Dependencies:** [CrossOver](https://www.codeweavers.com/crossover) (CrossOver 23+, 24+, or CrossOver Preview/GPTK) with at least one configured bottle.
- **Optional:** Bluetooth / USB Gamepad (Xbox One/Series, DualSense/PS5, DualShock 4, Nintendo Switch Pro, or MFi controllers).

---

## Installation & First Launch

Because GameHub is an independent, open-source project distributed without a paid Apple Developer certificate, it is signed using **ad-hoc signing** without Apple Notarization. macOS Gatekeeper will flag the download as untrusted upon initial opening.

### Quick Setup:
1. Extract `GameHub-v1.0.0-macOS.zip`.
2. Move `GameHub.app` into your `/Applications/` folder.
3. Open the app using either method below:

#### Method A (Finder):
- Right-click (or Control-click) `GameHub.app` in Finder.
- Select **Open** from the menu.
- In the confirmation dialog ("macOS cannot verify the developer..."), click **Open**.

#### Method B (Terminal):
Open Terminal and run the following command to remove the quarantine flag:
```bash
xattr -cr /Applications/GameHub.app
```
Then launch GameHub normally from Launchpad, Spotlight, or Finder.

---

## Key Features
- **PS5 Console Interface:** Fullscreen dark aesthetic, large hero backgrounds, fluid carousel shelf, and subtle UI sound effects.
- **Two Add Game Workflows:**
  - **Method A (Auto-Discover):** Scans CrossOver installations, lists available bottles (`EXE`, `Steam`, etc.), and auto-imports registered Windows shortcuts.
  - **Method B (Custom Browser):** Pick any `.exe`, `.lnk`, or `.app` on your internal drive or external SSD.
- **Artwork Search & Importer:** Integrated online cover art and widescreen backdrop downloader (queries public Steam Storefront data out-of-the-box, with optional SteamGridDB API key support).
- **External SSD Management:** Automatically detects disconnected external volumes, showing an amber badge and preventing broken launches instead of deleting your library entries.
- **Controller Support:** Native Apple GameController integration with optional Xbox layout correction (`SDL_GAMECONTROLLER_USE_BUTTON_LABELS=0`).

---

## Controls
| Input | Action |
|---|---|
| `←` / `→` / `↑` / `↓` or D-Pad | Navigate between games in your shelf |
| `Space` / `Return` / `Button A` | Launch selected game |
| `F` | Toggle favorite |
| `Cmd + N` | Open "Add Game" dialog |
| `Cmd + ,` | Open Settings & Diagnostics |

---

## Known Limitations
- **No In-Game Overlay:** GameHub manages your game library and launch execution; it does not inject an in-game HUD.
- **Ad-Hoc Signing:** Requires a one-time Gatekeeper bypass on macOS as documented above.
- **SteamGridDB API Key:** While official Steam Storefront artwork works without an account, SteamGridDB requires a free user API key (configurable in Settings).

---

## How to Report Bugs & Feedback
If you encounter crashes, discovery issues, or UI glitches:
1. Open GameHub Settings (`Cmd + ,`) and switch to the **Diagnostics** tab to see live activity.
2. Diagnostic logs are stored locally at:
   ```
   ~/Library/Application Support/GameHub/diagnostics.log
   ```
3. Share your feedback, log excerpts, macOS version, and controller model on Reddit.
