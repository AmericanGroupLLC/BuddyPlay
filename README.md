# BuddyPlay

[![CI](https://github.com/AmericanGroupLLC/BuddyPlay/actions/workflows/ci.yml/badge.svg?branch=master)](https://github.com/AmericanGroupLLC/BuddyPlay/actions/workflows/ci.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Android%20%7C%20iOS-blue.svg)](#stack)

> **Play anywhere. No internet needed.**

BuddyPlay is a lightweight, all-in-one **offline** multiplayer hub. Two
phones nearby — by Wi-Fi, mobile hotspot, or Bluetooth LE — pair and play
together. No accounts, no servers, no internet required. The "subway
tunnel works" experience is the USP.

| | iPhone | Android |
|---|---|---|
| Royal Chess (turn-based) | ✅ | ✅ |
| Dice Kingdom (Ludo-style) | ✅ | ✅ |
| Mini Racer (real-time twitch) | ✅ Wi-Fi/Hotspot | ✅ Wi-Fi/Hotspot |
| Local rivalries store | ✅ | ✅ |
| Connectivity ladder (Wi-Fi → Hotspot → BLE) | ✅ | ✅ |
| Cross-platform play (iOS ↔ Android) | ✅ | ✅ |

## Stack

- **Apple**: Swift / SwiftUI, iOS 17, XcodeGen.
- **Android**: Kotlin / Jetpack Compose, multi-module Gradle (`:core` + `:app`),
  Hilt, DataStore.
- **Backend**: **None.** Offline-first. No accounts, no servers, no analytics.
- **Shared logic**: `BuddyCore` Swift Package (Apple) and `:core` JVM Kotlin
  module (Android). Same models, mirrored case-for-case tests.

## Repo layout

```
shared/BuddyCore # Apple-side shared models + domain helpers + tests
ios/             # iPhone app
android/         # :core JVM + :app phone
.github/workflows# 6 workflows: ci, ios, android, marketing, pre-release-tests, release
scripts/         # local dev helpers (test-all, run-*-emulator, bump-version)
distribution/    # release whatsnew text per locale
```

See [`DESIGN.md`](DESIGN.md) for the full architecture,
[`CONNECTIVITY.md`](CONNECTIVITY.md) for the failover ladder + wire format,
and [`BUDDYPLAY-FEATURES.md`](BUDDYPLAY-FEATURES.md) for the feature inventory.

## Get started

```sh
# iOS Simulator
./scripts/run-ios-sim.sh

# Android emulator
./scripts/run-android-emulator.sh

# Run every test suite
./scripts/test-all.sh
```

## License

MIT — see [LICENSE](LICENSE).

## Related repos

Companion umbrella repo: [mobile-apps](https://github.com/AmericanGroupLLC/mobile-apps).
This repository was extracted from `AmericanGroupLLC/mobile-apps` via
`git subtree split` with full history preserved.

## Contributing

See [CONTRIBUTING.md](#) and the [issue templates](.github/ISSUE_TEMPLATE/) for
bug reports, feature requests, security disclosures, doc fixes, and questions.
