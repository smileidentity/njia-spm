# njia, the Swift package

[![Release](https://img.shields.io/github/v/release/smileidentity/njia-spm?label=release&logo=swift&logoColor=white&color=success)](https://github.com/smileidentity/njia-spm/releases/latest)
[![iOS](https://img.shields.io/badge/iOS-15.0%2B-blue?logo=apple&logoColor=white)](#requirements)
[![Swift](https://img.shields.io/badge/Swift-6.0%2B-F05138?logo=swift&logoColor=white)](#requirements)

The Swift Package Manager distribution of **njia**, the flow navigation engine behind the Smile ID
SDKs. This repository holds the `Package.swift` manifest, and each release carries the
xcframeworks it points at.

njia keeps a flow's back stack as engine state. An SDK describes its flow as a graph of steps, the
engine decides where next, back and skip go, and the host only draws the entries the engine holds.

> **Generated, not hand-edited.** Each njia release writes this README and the manifest, so a
> change made here is replaced by the next release.

## Requirements

- iOS 15.0 or later
- Swift 6.0 or later (Xcode 16 or later)

## Installation

In Xcode, choose **File → Add Package Dependencies…** and enter:

```
https://github.com/smileidentity/njia-spm
```

Or add it to your own `Package.swift`:

```swift
dependencies: [
    .package(url: "https://github.com/smileidentity/njia-spm", exact: "0.0.1-SNAPSHOT.2")
]
```

## Products

| Product | What it holds |
|---|---|
| `Njia` | The graph, state, intents and effects, the reducer, `NjiaEngine`, the delivery gate and the codec, behind the `NjiaKit` front door. Foundation only |
| `NjiaUI` | `NjiaHost`, the SwiftUI host, and `NjiaPreview` for `#Preview`s |
| `NjiaTesting` | `FakeNjiaNavigator` and `RecordingNjiaListener`, for test targets only |

Pin an exact version: the Flutter plugin `usesmileid_njia` and the React Native package
`@smileid/njia` each pin this package exactly at their own version, so an app that carries one of
them and the native SDK resolves one `Njia.framework`.

## Releases

Each [release](https://github.com/smileidentity/njia-spm/releases) carries the three xcframeworks
with their SHA-256 sums, and its notes list what changed. A snapshot is a prerelease named
`x.y.z-SNAPSHOT.N`, for testing only.

## License

MIT. See [LICENSE](LICENSE).
