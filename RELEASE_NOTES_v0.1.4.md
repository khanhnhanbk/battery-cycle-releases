# BatteryCycle 0.1.4 — Release Notes

Release date: 2026-10-24

## Download

- `BatteryCycle-0.1.4.apk` — install this on the phone.
- `BatteryCycle-0.1.4.aab` — Android App Bundle for future store upload; not directly installable.
- `SHA256SUMS.txt` — integrity checksums.

Requires Android 8.0+ (minSdk 26). No account, no ads, no internet permission.

## New: a card that looks like the Honor system cards

The home-screen card now sits next to the system cards as if it were one of them:

- **Same size and position as the Honor Clock card** in a 2×2 space.
- **Glass background** with a thin light edge, and white text, like the system cards.
- **Only what matters:**
  - the battery temperature in whole degrees (e.g. **35°**);
  - a **⚡ Charging** chip while charging, or **⚡ Full** when full and still plugged in (it hides when you unplug);
  - a big battery percent in your phone's system font.
- In the widget list the card is now called **Battery** (under BatteryCycle).
- Tap the card to open the app. Cycle count, health and history are in the app.

The app also asks the Honor launcher for its card blur and card stacking. Whether the launcher grants these to a non-Honor app is not confirmed yet. The launcher only reads these settings when a card is added, so to try them, remove the card and add it again.

The card does **not** start a foreground service or post a notification. It updates from battery/power broadcasts, the launcher's periodic update, app resume/refresh, and WorkManager samples. Launchers can throttle updates.

### Updating

Install over the existing app; your history is kept. The card already on your home screen picks up the new look automatically. If you still have the old 0.1.2 4×3 card, remove it and add **Battery** again to get the 2×2 size.

## Other changes

- 26 JVM tests.
- Version `0.1.4` (`versionCode 5`).

## Installation

1. Download `BatteryCycle-0.1.4.apk`.
2. Allow “Install unknown apps” for the browser/file manager.
3. Install over an existing **release-signed** 0.1.x install; local history is preserved.
4. If a **debug-signed** app is installed, uninstall it first. Android rejects a differently signed package, and uninstalling removes local history.

## Verification

APK SHA-256:

```text
9acaf04e5cd2a0ebc03fdfc0e169c0bb70002c88a2c547dc0a77ab8254c94ff5  BatteryCycle-0.1.4.apk
```

AAB SHA-256:

```text
aff7c0644236bc9a9d487d1f43499969d3a53f8835ff871441e9582725947c91  BatteryCycle-0.1.4.aab
```

Signing certificate SHA-256 (unchanged since 0.1.1):

```text
123a0dd76be7fa32a1ab89c4b0d72b2f99218172b51860187ad4e266263a0d9d
```

Check on Windows:

```powershell
Get-FileHash .\BatteryCycle-0.1.4.apk -Algorithm SHA256
```

## Known limitations

- Launcher blur and stacking for this card are not confirmed; without blur the card is a light glass tint over the wallpaper.
- The card size is tuned to the Honor X9d; other launchers may show it at a different size than their system cards.
- Cycle count is OEM-dependent. Health is an estimate, not a factory diagnostic.
- WorkManager and launchers can delay updates; the card is not a real-time monitor.
- Oppo Find X9 has not been probed.
- GitHub and a future Google Play build may be separate signing channels.

## Privacy

All data is local. There is no internet permission, account, analytics, ads, or cloud sync. See `PRIVACY.md`.

## Source

The source repository is private. This release contains the signed binary, checksums, privacy policy, and notices only.
