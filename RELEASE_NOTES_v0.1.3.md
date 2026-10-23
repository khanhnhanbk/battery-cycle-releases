# BatteryCycle 0.1.3 — Release Notes

Release date: 2026-10-23

## Download

- `BatteryCycle-0.1.3.apk` — install this on the phone.
- `BatteryCycle-0.1.3.aab` — Android App Bundle for future store upload; not directly installable.
- `SHA256SUMS.txt` — integrity checksums.

Requires Android 8.0+ (minSdk 26). No account, no ads, no internet permission.

## New: 2×2 glass card

The home-screen card is now a small **2×2** card in the style of the Honor system cards:

- Big battery percent.
- Battery temperature.
- A small ⚡ bolt while charging (also when full and still plugged in).
- Frosted-glass background: translucent white tint, soft sheen, and a light border, so the wallpaper shows through.
- Tap to open the app.

Cycle count, health, rated capacity, and history are still in the app; they are no longer on the card.

### Updating from 0.1.2

A card that is already on the home screen keeps its old 4×3 size. To get the 2×2 card:

1. Long-press the old card and remove it.
2. Long-press an empty area → **Widgets/Cards** → **BatteryCycle**.
3. Drag **BatteryCycle card** onto the home screen. It takes 2×2 cells.

### Stacking and transparency

- The card has a fixed 2×2 size, which is what MagicOS needs to place it next to, or stack it with, other 2×2 cards. Stacking itself is a launcher feature: drag the card onto another 2×2 card to try it.
- Android widgets cannot blur the wallpaper. Honor's own blur only applies to its system cards, so this card fakes the glass with transparency instead.

The card does **not** start a foreground service or post a notification. It updates from battery/power broadcasts, the launcher's periodic update, app resume/refresh, and WorkManager samples. Launchers can throttle updates.

## Other changes

- The card reads only the sticky battery broadcast, so it updates faster.
- Widget formatting is covered by four JVM tests; suite is now 25 tests.
- Version `0.1.3` (`versionCode 4`).

## Installation

1. Download `BatteryCycle-0.1.3.apk`.
2. Allow “Install unknown apps” for the browser/file manager.
3. Install over an existing **release-signed** 0.1.1/0.1.2 install; local history is preserved.
4. If a **debug-signed** app is installed, uninstall it first. Android rejects a differently signed package, and uninstalling removes local history.

## Verification

APK SHA-256:

```text
52d17952265bff46d9f32a5512f553135c6e35542b603e0aadae3d9c33cac00d  BatteryCycle-0.1.3.apk
```

AAB SHA-256:

```text
6c69e0b963c1651feb65f69dd56b7972dc833b55cea488944b11f668203591ff  BatteryCycle-0.1.3.aab
```

Signing certificate SHA-256 (unchanged since 0.1.1):

```text
123a0dd76be7fa32a1ab89c4b0d72b2f99218172b51860187ad4e266263a0d9d
```

Check on Windows:

```powershell
Get-FileHash .\BatteryCycle-0.1.3.apk -Algorithm SHA256
```

## Known limitations

- The glass look is transparency, not a real blur.
- Whether MagicOS lets this card join a card stack depends on the launcher.
- Cycle count is OEM-dependent. Health is an estimate, not a factory diagnostic.
- WorkManager and launchers can delay updates; the card is not a real-time monitor.
- Oppo Find X9 has not been probed.
- GitHub and a future Google Play build may be separate signing channels.

## Privacy

All data is local. There is no internet permission, account, analytics, ads, or cloud sync. See `PRIVACY.md`.

## Source

The source repository is private. This release contains the signed binary, checksums, privacy policy, and notices only.
