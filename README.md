# VRization iPhone build

Builds an unsigned physical-iPhone IPA from [LexZeon/VRization](https://github.com/LexZeon/VRization), pinned to commit `56f9db52bfb56edfdea92c1864f6bee28fa4f28f` (SteamVR preview 0.5.1/build 3).

## Build

The workflow runs on a standard GitHub-hosted macOS runner. It tests both Swift cores, builds using the physical iPhone SDK, validates an arm64 iOS executable, and packages `VRization-SteamVR-unsigned.ipa`. It never receives Apple account credentials or signing certificates. Build logs, source identity, licenses and a SHA-256 checksum accompany the artifact.

See [Actions](../../actions). A green workflow result means software checks and compilation passed; it does not mean physical hardware testing passed. Download the `VRization-iPhone-unsigned` artifact from a successful run and extract the IPA. Failed runs may contain only diagnostics.

## Install later on Windows

Sign and install the unsigned IPA locally with your own Apple account using [Sideloadly](https://sideloadly.io/). Enter account credentials yourself in that application. Free signing normally needs refreshing every seven days. Device trust, Developer Mode and signing compatibility may need attention during the first installation.

The iPhone app requires a matching Windows VRization SteamVR host. A successful iOS build alone is not a complete, tested game setup. USB is the intended first connection route to avoid relying on school Wi-Fi peer connectivity.

## Scope

- Phone-based orientation tracking first.
- AirPods/HeadTrack integration is a later goal and is not implemented by this workflow.
- No physical iPhone, lens fit, USB, SteamVR game, War Thunder, sustained frame rate or latency results have been established by this build configuration.
- No runtime application source is changed; this repository automates building and packaging upstream code. It is not affiliated with the upstream authors.
