# Cutroom releases

Official downloads for **Cutroom**, the desktop video editor you drive with your own AI (by Delivvo).
The source code is private; this repository only hosts the installers and the auto-update feeds.

Get a licence and sign in at [delivvo.io/cutroom](https://delivvo.io/cutroom).

## Download the latest version

| Platform | Download |
|---|---|
| Windows 10/11 (x64) | [Cutroom-Setup-x64.exe](https://github.com/Mohammed3382/cutroom-releases/releases/latest/download/Cutroom-Setup-x64.exe) |
| macOS (Apple Silicon, M1 or newer) | [Cutroom-mac-arm64.dmg](https://github.com/Mohammed3382/cutroom-releases/releases/latest/download/Cutroom-mac-arm64.dmg) |

These links always point to the newest release. Every release also carries a copy with the version in the
file name (for example `Cutroom-Setup-x64-0.12.1.exe`, `Cutroom-mac-arm64-0.12.1.dmg`).

## Updates

- **Windows:** the app checks this feed (`latest.yml`) on launch and every few hours, downloads the update in
  the background, and asks you to restart. Your projects and settings are untouched.
- **macOS:** the app checks this feed (`latest-mac.yml`) and shows a banner with a **Download** button when a
  new version is out. Open the new disk image and drag Cutroom to Applications, replacing the old one. Your
  projects and settings are untouched. (Automatic in-place install arrives once the Mac build is notarized.)

## Installing on macOS

The Mac build is not yet notarized by Apple. The first time, open Applications, right-click Cutroom and
choose **Open**, then confirm. After that it opens normally.

## Assets on every release

| File | Purpose |
|---|---|
| `Cutroom-Setup-x64.exe` | Windows installer (stable name, used by the website and the updater) |
| `Cutroom-Setup-x64-<version>.exe` | The same installer, named with its version |
| `Cutroom-Setup-x64.exe.blockmap` | Lets Windows updates download only what changed |
| `latest.yml` | Windows update feed |
| `Cutroom-mac-arm64.dmg` | macOS disk image (stable name) |
| `Cutroom-mac-arm64-<version>.dmg` | The same disk image, named with its version |
| `Cutroom-mac-arm64.zip` | macOS app archive (used by the updater) |
| `latest-mac.yml` | macOS update feed |

Release notes for each version are on the [Releases](https://github.com/Mohammed3382/cutroom-releases/releases) page.
