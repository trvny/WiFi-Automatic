# Changelog

All notable changes to this project are documented here. The format is based on
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project adheres
to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [2.0.0] - 2026-06-17

First release of the `travino` fork, consolidating work from three upstream forks
and modernizing the build to a current toolchain.

### Added
- GitHub Actions CI (builds `assembleFdroidDebug` as the compile gate) and a tagged
  release workflow that builds and signs the APK.
- Dependabot coverage for the Gradle and GitHub Actions ecosystems.

### Changed
- Migrated the app to AndroidX: `appcompat-v7`/`recyclerview-v7` replaced with
  `androidx.appcompat:appcompat:1.7.1`, `androidx.recyclerview:recyclerview:1.3.2`,
  and `androidx.core:core:1.13.1`; all `android.support.*` references rewritten.
- Upgraded the build toolchain to Android Gradle Plugin 9.0.1 / Gradle 9.1.0 on JDK 17.
- Raised `compileSdk` to 35. `targetSdk` is intentionally held at 28 to preserve the
  current runtime behavior (including programmatic Wi-Fi toggling) on Android 9.
- Fixed Bluetooth preference handling.

### Removed
- Dropped support for Android versions below 5.0 (`minSdk` raised from 14 to 21,
  the floor required by AndroidX appcompat 1.7).

### Fixed
- Replaced the legacy Travis configuration and resolved AGP 9 build-gate issues
  (non-final R class, proguard defaults, manifest `<uses-sdk>` removal).

[2.0.0]: https://github.com/travino/WiFi-Automatic/releases/tag/v2.0.0
