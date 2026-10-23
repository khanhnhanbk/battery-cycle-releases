# BatteryCycle — Privacy and Data Handling

BatteryCycle is a local-only app. This document explains what it stores and what it does not do.

## Data stored on the phone

- Battery samples: timestamp, level, status, plug type, health code, temperature, voltage, current, charge counter, energy counter, optional cycle count, optional design/max capacity.
- Charge sessions: start/end times, levels, energy added, energy source, sample count, optional estimated capacity.
- Settings: rated capacity, sampling enabled/interval, theme.

These are stored in the app's private Room database and Preferences DataStore. They are not uploaded anywhere.

## Network access

The app has **no `INTERNET` permission**. It cannot make network requests. There are no ads, analytics, crash reporters, accounts, or cloud sync.

The merged manifest includes `ACCESS_NETWORK_STATE` because AndroidX WorkManager references it for constraint plumbing; that permission does not grant internet access and the app has no network code.

## Backups

`android:allowBackup="false"` is set. The app's database and settings are excluded from Android cloud backup. Uninstalling the app removes its history.

## Diagnostics

The Diagnostics screen displays raw device/battery values on the phone. The copy button places that text on the clipboard. The app does not transmit it.

## Permissions

Runtime permissions requested: **none**.

Library-contributed manifest permissions:

- `WAKE_LOCK` — WorkManager jobs.
- `RECEIVE_BOOT_COMPLETED` — WorkManager reschedule receiver.
- `ACCESS_NETWORK_STATE` — WorkManager constraint plumbing.
- `FOREGROUND_SERVICE` — WorkManager's library service declaration; the app never starts it.
- `DYNAMIC_RECEIVER_NOT_EXPORTED_PERMISSION` — AndroidX receiver safety.

## Developer/ADB access

Installing via ADB is a developer action, not app data collection. The app contains no exported services, receivers, or providers. Only the launcher Activity is exported.

## Third parties

No third-party SDKs collect data. The app uses open-source AndroidX/Kotlin libraries locally; see `THIRD_PARTY_NOTICES.md`.

## Changes

If a future version adds network access, export/cloud features, analytics, or notifications, this document and the app's permission list must be updated before release.
