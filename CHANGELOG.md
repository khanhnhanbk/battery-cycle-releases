# Changelog

## 0.1.3 — 2026-10-23

- Home-screen card is now a fixed **2×2** card that fits beside MagicOS system cards and can be offered to card stacks.
- Card shows only battery percent and temperature, plus a small ⚡ while charging.
- Translucent frosted-glass background (transparency; Android widgets cannot blur the wallpaper).
- Card updates faster: it reads only the battery broadcast.
- Four widget formatting tests; 25 JVM tests total.
- Version `0.1.3` (`versionCode 4`).

## 0.1.2 — 2026-10-23

- Added the 4×3 home-screen card: level, status, temperature, hardware cycles, estimated health, rated capacity, last update.
- Honor `MTN-NX1` device label renders as **Honor X9d**.
- Widget refreshes on battery/power/boot broadcasts, app refresh, settings changes, and WorkManager samples.
- Six widget formatting tests; 27 JVM tests total.
- Version `0.1.2` (`versionCode 3`).

## 0.1.1 — 2026-10-23

- Signed release APK and AAB.
- Honor mAh-like charge-counter normalization.
- GitHub Releases distribution.
- Public release notes, checksums, privacy policy, and third-party notices.
- No internet permission; no app-started foreground service or notification.

## 0.1.0 — 2026-10-23

- Initial BatteryCycle app: dashboard, hardware cycle count when exposed, charge history, estimated capacity/health, diagnostics.
- WorkManager charging samples and daily maintenance.
- Local-only Room + DataStore storage.
- No account, ads, analytics, or cloud.
