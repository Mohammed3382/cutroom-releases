# Cutroom releases

Official downloads for **Cutroom**, the desktop video editor you drive with your own AI (by Delivvo).
The source code is private; this repository only hosts the installers and the auto-update feeds.

Get a licence and sign in at [delivvo.io/cutroom](https://delivvo.io/cutroom).

## What it is

Cutroom is a local video editor for Windows and Mac with a built-in **MCP server**. Edit by hand on a
normal timeline, or let Claude Code, Claude Desktop, Codex, Cursor or any other MCP client make the edit
while you watch the clips land on your timeline. Editing, transcription and export run on your own computer.

- **Price:** $12 a month or $99 a year at [delivvo.io/cutroom](https://delivvo.io/cutroom). Cancel any time.
- **Licence:** proprietary. The source is private; this repository hosts the official installers.

## MCP server

Cutroom ships a standard stdio MCP server. It forwards your AI client's tool calls to the running app and
exposes editing features only: no shell, no arbitrary file access, no access to the app's code. Your own
client does the thinking on your own account, so Cutroom spends nothing on AI for you.

**Connect it:** open Cutroom, open a project, and use the in-app **Connect Claude** panel. It registers
the server with Claude Code, Claude Desktop or Codex for you. Manual setup, if you prefer: point your client
at the bundled `resources/mcp/cutroom-mcp.mjs` inside the Cutroom install folder and run it with Node 18+.

```sh
claude mcp add cutroom -- node "<Cutroom install folder>/resources/mcp/cutroom-mcp.mjs"
```

**What your AI can do (120+ tools), grouped:**

| Area | Examples |
|---|---|
| Cutting | import clips, place and trim on the timeline, remove silence and filler words, speed ramps, freeze frames |
| Captions | word-by-word captions in 90+ languages, 27 styles, right to left for Arabic |
| Look | colour grade, exposure, curves, LUT-style looks, background removal, chroma key, masks |
| Sound | noise reduction, loudness to -14 LUFS, music ducking under voice, voiceover |
| Graphics | titles, lower thirds, counters, callouts, transitions, motion paths |
| Checking | `render_frame`, `watch_pass` and `screenshot` return real frames, so a vision model sees what it made |
| Export | TikTok, Shorts, YouTube and LinkedIn presets in one pass; originals are never touched |

If the app is closed, the server answers with one help tool that says to open Cutroom, and never crashes.

## Download the latest version

| Platform | Download |
|---|---|
| Windows 10/11 (x64) | [Cutroom-Setup-x64.exe](https://github.com/Mohammed3382/cutroom-releases/releases/latest/download/Cutroom-Setup-x64.exe) |
| macOS on Apple Silicon (M1 or newer) | [Cutroom-mac-arm64.dmg](https://github.com/Mohammed3382/cutroom-releases/releases/latest/download/Cutroom-mac-arm64.dmg) |
| macOS on Intel | [Cutroom-mac-x64.dmg](https://github.com/Mohammed3382/cutroom-releases/releases/latest/download/Cutroom-mac-x64.dmg) |

Not sure which Mac you have? Apple menu > About This Mac: "Chip: Apple M…" is Apple Silicon, "Processor: Intel" is Intel.
macOS 12 Monterey or newer.

These links always point to the newest release. Every release also carries a copy with the version in the
file name (for example `Cutroom-Setup-x64-0.12.2.exe`, `Cutroom-mac-arm64-0.12.2.dmg`, `Cutroom-mac-x64-0.12.2.dmg`).

## Updates

- **Windows:** the app checks this feed (`latest.yml`) on launch and every few hours, downloads the update in
  the background, and asks you to restart. Your projects and settings are untouched.
- **macOS:** the app checks this feed (`latest-mac.yml`) and shows a banner with a **Download** button when a
  new version is out (it downloads the disk image for your Mac). Open it and drag Cutroom to Applications,
  replacing the old one. Your projects and settings are untouched.

## Installing on macOS

1. Open the disk image and drag **Cutroom** into **Applications**. Open it from Applications (not from the
   disk image or Downloads).
2. The Mac build is not yet notarized by Apple, so the first launch is blocked once:
   - **macOS 15 Sequoia and newer:** open Cutroom, click **Done** on the warning, then go to
     **System Settings > Privacy & Security**, scroll down to the message about Cutroom and click
     **Open Anyway**, then confirm with your password.
   - **macOS 12 to 14:** in Applications, right-click (or Control-click) Cutroom, choose **Open**, then **Open**.
   After that it opens normally.
3. The first time you record, macOS asks for **Camera** and **Microphone** access (allow them). Screen
   recording needs **System Settings > Privacy & Security > Screen & System Audio Recording** with Cutroom
   turned on; Cutroom opens that page for you if it is off. Quit and reopen Cutroom after turning it on.
4. If macOS asks to let Cutroom use "cutroom Safe Storage" in your keychain, choose **Always Allow**: that is
   where your API keys and sign-in are kept, encrypted.

## Assets on every release

| File | Purpose |
|---|---|
| `Cutroom-Setup-x64.exe` | Windows installer (stable name, used by the website and the updater) |
| `Cutroom-Setup-x64-<version>.exe` | The same installer, named with its version |
| `Cutroom-Setup-x64.exe.blockmap` | Lets Windows updates download only what changed |
| `latest.yml` | Windows update feed |
| `Cutroom-mac-arm64.dmg` / `Cutroom-mac-x64.dmg` | macOS disk images, Apple Silicon / Intel (stable names) |
| `Cutroom-mac-arm64-<version>.dmg` / `Cutroom-mac-x64-<version>.dmg` | The same disk images, named with their version |
| `Cutroom-mac-arm64.zip` / `Cutroom-mac-x64.zip` | macOS app archives |
| `latest-mac.yml` | macOS update feed |

Release notes for each version are on the [Releases](https://github.com/Mohammed3382/cutroom-releases/releases) page.
