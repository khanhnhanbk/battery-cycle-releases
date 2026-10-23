# BatteryCycle 0.1.2 — Release Notes

Release date: 2026-10-23

## Download

- `BatteryCycle-0.1.2.apk` — install this on the phone.
- `BatteryCycle-0.1.2.aab` — Android App Bundle for future store upload; not directly installable.
- `SHA256SUMS.txt` — integrity checksums.

Requires Android 8.0+ (minSdk 26). No account, no ads, no internet permission.

## New: Honor home-screen card

BatteryCycle now includes a **4×3 home-screen widget**:

- Current level and progress bar.
- Charging/discharging status.
- Battery temperature.
- Hardware cycle count (the Honor X9d shows **104**).
- Estimated health, when enough charge data exists.
- Rated capacity and last-update age.
- Tap to open the app.

Add it on the Honor:

1. Long-press an empty area of the home screen.
2. Tap **Widgets** (MagicOS may call it **Cards**).
3. Find **BatteryCycle**.
4. Drag **BatteryCycle card** onto the home screen.

The card does **not** start a foreground service or post a notification. It updates from battery/power broadcasts, the launcher's periodic update, app resume/refresh, settings saves, and WorkManager samples. Launchers can throttle updates; open the app or tap Refresh for an immediate update.

## Other changes

- Device label maps `MTN-NX1` to **Honor X9d**.
- Widget formatting is covered by six JVM tests; suite is now 27 tests.
- Version `0.1.2` (`versionCode 3`).

## Installation

1. Download `BatteryCycle-0.1.2.apk`.
2. Allow “Install unknown apps” for the browser/file manager.
3. Install over an existing **release-signed** 0.1.1 install; local history is preserved.
4. If a **debug-signed** app is installed, uninstall it first. Android rejects a differently signed package, and uninstalling removes local history.

## Verification

APK SHA-256:

```text
6e3c22ceb1e1bbc172ba3fc4e8fdc6e7ff593ef924966ea953e70b6b65e85e30  BatteryCycle-0.1.2.apk
```

AAB SHA-256:

```text
b2f896cf44507e6c41e0fea4925f9cdc39c0bc0d1bd0c758837125eb0c3f3ea7  BatteryCycle-0.1.2.aab
```

Signing certificate SHA-256 (unchanged from 0.1.1):

```text
123a0dd76be7fa32a1ab89c4b0d72b2f99218172b51860187ad4e266263a0d9d
```

Check on Windows:

```powershell
Get-FileHash .\BatteryCycle-0.1.2.apk -Algorithm SHA256
```

## Known limitations

- Widget placement/update behavior has not yet been verified on a physical MagicOS launcher; the code, layout, manifest, and format tests pass.
- Cycle count is OEM-dependent. The Honor X9d exposes 104; some phones do not.
- Design capacity is not public; the Honor requires manual rated-capacity input (8,300 mAh if that matches the phone's rated spec).
- Health is an estimate, not a factory diagnostic.
- WorkManager and launchers can delay updates; the card is not a real-time monitor.
- Oppo Find X9 has not been probed.
- GitHub and a future Google Play build may be separate signing channels.

## Privacy

All data is local. There is no internet permission, account, analytics, ads, or cloud sync. See `PRIVACY.md`.

## Source

The source repository is private. This release contains the signed binary, checksums, privacy policy, and notices only.
