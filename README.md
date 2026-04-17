<p align="center">
  <img src="images/banner.png" alt="MacFansControl" width="100%">
</p>

<p align="center">
  <strong>Native macOS fan control for Apple Silicon and Intel</strong><br>
  Monitor every temperature sensor. Set precise fan speeds. Reduce noise during light work, maximize cooling under heavy loads.
</p>

<p align="center">
  <a href="https://github.com/beyondthecode-bc/MacFansControl/releases/latest"><img src="https://img.shields.io/github/v/release/beyondthecode-bc/MacFansControl?style=flat-square&label=Download&color=blue" alt="Latest Release"></a>
  <a href="https://github.com/beyondthecode-bc/MacFansControl/releases/latest"><img src="https://img.shields.io/github/downloads/beyondthecode-bc/MacFansControl/total?style=flat-square&label=Downloads&color=brightgreen" alt="Downloads"></a>
  <a href="https://github.com/beyondthecode-bc/MacFansControl/stargazers"><img src="https://img.shields.io/github/stars/beyondthecode-bc/MacFansControl?style=flat-square" alt="Stars"></a>
  <img src="https://img.shields.io/github/license/beyondthecode-bc/MacFansControl?style=flat-square" alt="License">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/platform-macOS%2014%2B-lightgrey?style=flat-square&logo=apple" alt="Platform">
  <img src="https://img.shields.io/badge/chip-Apple%20Silicon%20%2B%20Intel-orange?style=flat-square&logo=apple" alt="Apple Silicon + Intel">
  <img src="https://img.shields.io/badge/swift-6.1-F05138?style=flat-square&logo=swift&logoColor=white" alt="Swift">
  <img src="https://img.shields.io/badge/SwiftUI-native-007AFF?style=flat-square&logo=swift&logoColor=white" alt="SwiftUI">
  <img src="https://img.shields.io/badge/languages-8-green?style=flat-square&logo=translate" alt="Languages">
</p>

<p align="center">
  <a href="https://www.virustotal.com/gui/file/597e09ab642f08b9a136371dd8053b1b379c9b25facb6ad31e97a9b8e8d24563"><img src="https://img.shields.io/badge/VirusTotal-0%2F66%20Clean-brightgreen?style=flat-square&logo=virustotal&logoColor=white" alt="VirusTotal"></a>
  <a href="https://github.com/sponsors/beyondthecode-bc"><img src="https://img.shields.io/badge/Sponsor-%E2%9D%A4-pink?style=flat-square&logo=github" alt="GitHub Sponsors"></a>
  <a href="https://www.buymeacoffee.com/BEYONDTHECODE"><img src="https://img.shields.io/badge/Buy%20Me%20a%20Coffee-FFDD00?style=flat-square&logo=buymeacoffee&logoColor=black" alt="Buy Me a Coffee"></a>
</p>

<p align="center">
  Built with Swift and SwiftUI. No Electron, no web views, no bloat.
</p>

---

## Screenshots

<p align="center">
  <img src="images/screenshot-menubar.png" alt="Menu bar dropdown" width="220">
  &nbsp;&nbsp;
  <img src="images/screenshot-sensors.png" alt="Sensors settings" width="520">
</p>

<p align="center">
  <img src="images/screenshot-fans.png" alt="Fan control settings" width="520">
  &nbsp;&nbsp;
  <img src="images/screenshot-general.png" alt="General settings" width="520">
</p>

---

## Download

Download the latest version from [**Releases**](https://github.com/beyondthecode-bc/MacFansControl/releases/latest). Unzip, move `MacFansControl.app` to Applications, and launch.

The app includes a built-in update checker — go to **Settings → About → Check Now** to see if a newer version is available and download it directly.

### Verification

Every release is scanned on [VirusTotal](https://www.virustotal.com) before publishing. You can verify the download yourself:

| | |
|---|---|
| **SHA-256** | `597e09ab642f08b9a136371dd8053b1b379c9b25facb6ad31e97a9b8e8d24563` |
| **VirusTotal Report** | [View full scan results](https://www.virustotal.com/gui/file/597e09ab642f08b9a136371dd8053b1b379c9b25facb6ad31e97a9b8e8d24563) |

To verify the hash locally: `shasum -a 256 MacFansControl.zip`

## Features

**Temperature Monitoring**
- Full sensor suite: CPU cores, GPU, SSD, battery, power regulators, ambient
- Real-time readings in the menubar with customizable display format
- Pin favorite sensors or category averages to the menubar

**Fan Control**
- Set exact RPM for any fan via slider
- Link fans to temperature sensors with custom curves (min/max temp-to-RPM mapping)
- Visual multi-point fan curve editor
- One-click return to automatic (system-controlled) mode

**Safety**
- Watchdog process returns fans to safe speeds if the app crashes or is force-quit
- Sleep/wake restoration re-applies your settings automatically
- Fans always return to automatic on clean quit

**Presets**
- Save and switch between named fan configurations
- Set a default preset that auto-applies on launch

**Preferences**
- Tabbed settings window: General, Sensors, Fans, Presets, Menu Bar, About, Disclaimer
- Drag-reorder favorites, hide sensors, copy Markdown snapshots
- Favorite category averages (CPU avg, GPU avg) for cleaner monitoring
- Launch at login, dock icon toggle, temperature unit (C/F)
- Per-app language override

**Localization**
- 8 languages: English, French, German, Spanish, Japanese, Korean, Portuguese (Brazilian), Chinese (Simplified)
- Community translations welcome via pull requests

## Supported Chips

| Generation | Variants |
|---|---|
| **M1** | M1, M1 Pro, M1 Max, M1 Ultra |
| **M2** | M2, M2 Pro, M2 Max, M2 Ultra |
| **M3** | M3, M3 Pro, M3 Max, M3 Ultra |
| **M4** | M4, M4 Pro, M4 Max, M4 Ultra |
| **M5** | M5, M5 Pro, M5 Max, M5 Ultra |
| **Intel** | Coffee Lake, Whiskey Lake, Ice Lake (Mac mini, iMac, and generic Intel Macs) |

## Requirements

| | Requirement |
|---|---|
| **OS** | macOS 14.0 (Sonoma) or later |
| **Chip** | Any Apple Silicon or supported Intel Mac |

## Getting Started

### 1. Install the app

Download and move `MacFansControl.app` to your Applications folder.

### 2. Install the Background Helper

On first launch, open **Preferences > General** and click **Install Helper**.

The background helper allows MacFansControl to change fan speeds without asking for your password every time. Since the app is not yet signed with an Apple Developer certificate (coming soon), macOS will prompt for your administrator password during installation. This is a one-time setup — once installed, fan control works silently in the background.

> **Why is this needed?** Changing fan speeds requires elevated (root) privileges. The helper runs as a small background service that handles these privileged operations securely via XPC, so the main app never needs root access itself.

### 3. Use the menubar

MacFansControl lives in your menubar. Click the temperature readout to see sensors, fans, presets, and quick access to preferences.

## Translations

This repository hosts the translation files for MacFansControl. You can help translate the app into your language or improve existing translations.

### How to contribute

1. Fork this repository
2. Edit an existing file in the [`languages/`](languages/) folder, or create a new one by copying `English.xml`
3. Translate the string values (the text between `<string>` tags) — **do not** change the `id` attributes
4. Keep any `%1`, `%2`, `%@`, `%d` placeholders in place — the app needs them
5. Submit a pull request

### Current languages

| Language | File | Status |
|---|---|---|
| English | [`English.xml`](languages/English.xml) | Complete |
| French | [`French.xml`](languages/French.xml) | Complete |
| German | [`German.xml`](languages/German.xml) | Complete |
| Spanish | [`Spanish.xml`](languages/Spanish.xml) | Complete |
| Japanese | [`Japanese.xml`](languages/Japanese.xml) | Complete |
| Korean | [`Korean.xml`](languages/Korean.xml) | Complete |
| Portuguese (BR) | [`Portuguese_Brazilian.xml`](languages/Portuguese_Brazilian.xml) | Complete |
| Chinese (Simplified) | [`Chinese_Simplified.xml`](languages/Chinese_Simplified.xml) | Complete |

Want to add a new language? Copy `English.xml`, rename it to your language name, translate the values, and submit a PR.

## Bug Reports & Feature Requests

Please use [Issues](../../issues) to report bugs or request features.

## Support the Project

If MacFansControl saves you from fan noise or thermal throttling, consider supporting development:

<p align="center">
  <a href="https://github.com/sponsors/beyondthecode-bc">
    <img src="https://img.shields.io/badge/Sponsor_on_GitHub-%E2%9D%A4-pink?style=for-the-badge&logo=github" alt="GitHub Sponsors" height="40">
  </a>
  &nbsp;&nbsp;&nbsp;
  <a href="https://www.buymeacoffee.com/BEYONDTHECODE">
    <img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" height="50">
  </a>
</p>

---

## Troubleshooting

### "MacFansControl" Not Opened — Gatekeeper warning

MacFansControl is not yet notarized with Apple (Apple Developer certificate coming soon). On first launch you may see this dialog:

<p align="center">
  <img src="images/gatekeeper-not-opened.png" alt="MacFansControl Not Opened dialog" width="220">
</p>

**To fix this:**

1. Click **Done** to dismiss the dialog
2. Open **System Settings > Privacy & Security**
3. Scroll down — you'll see a message that MacFansControl was blocked
4. Click **Open Anyway**

<p align="center">
  <img src="images/gatekeeper-blocked.png" alt="Open Anyway in Privacy and Security" width="420">
</p>

This only needs to be done once. After that, the app will open normally.

### Password prompt every time I change fan speed

You need to install the background helper. Go to **Preferences > General** and click **Install Helper**. The helper runs as a privileged background service so you won't be asked for your password on every fan speed change.

Since the app doesn't have an Apple Developer certificate yet, macOS will ask for your administrator password once during helper installation. This is expected and safe — the helper is a small daemon that only handles fan speed writes via the SMC interface.

### "Could not move to Applications" — read-only volume error

If you launch the app directly from the downloaded zip without extracting it first, you may see this error:

<p align="center">
  <img src="images/move-to-apps-error.png" alt="Could not move to Applications" width="220">
</p>

**To fix this:**

1. Close MacFansControl if it's running
2. Extract the zip file first (double-click the `.zip` in Finder)
3. Drag `MacFansControl.app` from the extracted folder to your **Applications** folder manually
4. Launch from Applications

This happens because macOS mounts zip contents as a read-only volume — the app can't move itself from there.

### Administrator password required when installing an update

When you click **Install Now** in **Settings → About**, macOS will show a password prompt before replacing the app in `/Applications`. This is expected — the app needs elevated permissions to overwrite itself.

<p align="center">
  <img src="docs/troubleshooting-update-permission.png" alt="Install failed: MacFansControl couldn't be removed because you don't have permission to access it." width="520">
</p>

> If you see the error above ("couldn't be removed because you don't have permission") instead of a password prompt, you are on **v1.1.2 or earlier**. Download **v1.1.3** or later from [Releases](https://github.com/beyondthecode-bc/MacFansControl/releases/latest) and install it manually — the issue is fixed in that version.

Use a macOS account with **Administrator** rights. On most personal Macs this is the default. If you are on a managed or work Mac with a Standard account, either ask your IT admin to install the update or download the zip from [Releases](https://github.com/beyondthecode-bc/MacFansControl/releases/latest) and replace the app manually.

### The app doesn't appear after launching

MacFansControl is a **menubar app** — it doesn't open a window on launch. Look for the temperature readout in your menubar (top-right area of the screen). If you don't see it, it may be hidden behind the notch on newer MacBooks — try closing other menubar apps to make room.

### Fans show 0 RPM

This usually means the background helper isn't installed or isn't running. Go to **Preferences > General** — if the helper status shows "not installed", click **Install Helper**. If it shows installed but fans still read 0 RPM, try clicking **Reinstall Helper**.
