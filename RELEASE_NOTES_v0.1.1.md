# BatteryCycle 0.1.1 — Release Notes

Release date: 2026-10-23

## Download

- `BatteryCycle-0.1.1.apk` — install this on the phone.
- `BatteryCycle-0.1.1.aab` — Android App Bundle for future store upload; not directly installable.
- `SHA256SUMS.txt` — integrity checksums.

Requires Android 8.0+ (minSdk 26). No account, no ads, no internet permission.

## Highlights

- Shows the phone's hardware battery cycle count when Android/OEM exposes it. Honor `MTN-NX1` reports **104**.
- Shows an estimated full capacity and health percentage after enough charge data.
- Keeps local charge-session history.
- Charges are sampled with WorkManager while charging; no persistent notification and no foreground service.
- **Honor fix:** Honor reports its charge counter in mAh-like units instead of µAh. This release normalizes that value using the current battery level.
- Rated capacity can be entered manually when Android does not expose design capacity.
- Diagnostics screen shows every raw battery extra/property for OEM troubleshooting.

## Installation

1. Download `BatteryCycle-0.1.1.apk` on the phone.
2. Allow installs from the browser/file manager (“Install unknown apps”).
3. If an older **debug-signed** BatteryCycle is installed, uninstall it first. Android will reject the release APK over a differently signed package.
   - Uninstalling removes the app's local history. Export/backup is not available in this release.
4. Install and open BatteryCycle.
5. Open **Settings → Rated battery capacity** and enter the phone's rated/design capacity. For the Honor X9d, use the exact rated figure from its specs (if it is 8,300 mAh, enter `8300`).
6. Open **Settings → Diagnostics** to see what your phone exposes.

## Verification

APK SHA-256:

```text
dac092c69e73c6a33de3f77b7618004aa6ef2bb7c88f34b02f29800e6fc97952  BatteryCycle-0.1.1.apk
```

AAB SHA-256:

```text
923df3a0da582b0cd535b315cc2c5ea796166c02b20016b93d37c6dff4a7cec7  BatteryCycle-0.1.1.aab
```

Signing certificate SHA-256:

```text
123a0dd76be7fa32a1ab89c4b0d72b2f99218172b51860187ad4e266263a0d9d
```

Signer DN: `CN=BatteryCycle, OU=Personal, O=khanhnhanbk, L=Ho Chi Minh City, ST=Ho Chi Minh, C=VN`

Check an APK on Windows:

```powershell
Get-FileHash .\BatteryCycle-0.1.1.apk -Algorithm SHA256
```

## Known limitations

- Cycle count is OEM-dependent. Some phones do not expose `EXTRA_CYCLE_COUNT`; the app then estimates.
- Design capacity is not public. Honor requires manual rated-capacity input.
- Health is an estimate, not a factory diagnostic. Do not use it for warranty or safety decisions.
- WorkManager is inexact; OEM battery managers can delay sampling.
- No persistent notification by design.
- Oppo Find X9 has not been probed yet.
- GitHub APK and a future Google Play build may use different signing keys; they are separate install channels.

## Privacy

All data is local. There is no internet permission, account, analytics, ads, or cloud sync. See `PRIVACY.md`.

## Source

The source repository is private. This release contains the signed binary, checksums, privacy policy, and notices only.
