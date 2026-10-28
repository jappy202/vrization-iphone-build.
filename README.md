# VRization iPhone build

Builds an unsigned physical-iPhone IPA from [LexZeon/VRization](https://github.com/LexZeon/VRization), pinned to commit `56f9db52bfb56edfdea92c1864f6bee28fa4f28f` (SteamVR preview 0.5.1), with the personal customization in `patches/phone-fit.patch`. Upstream license and attribution are preserved. This repository is not affiliated with the upstream authors.

## Build 4 changes

Four independent phone-local sliders adjust left/right horizontal and vertical placement. Positive horizontal moves right; positive vertical moves up. Values save automatically and have their own reset button. The Metal image and editor outlines use the same local corrections. Shared Windows settings and head orientation are unchanged.

Hide Settings discards/closes an active editor. Long-press outside the editor toolbar for 0.8 seconds to discard its draft and return to settings. Save and Discard also close the editor. Host tracking-pause semantics remain; use Refresh or PC Resume as needed.

The build runs Swift core tests, compiles for the physical iPhone SDK, and runs a focused native Simulator test for per-eye control independence, saved calibration after relaunch and editor exits. A successful software check does not prove physical optics, the exact reported overlay symptom, USB/LAN reliability, game compatibility or performance.

## Download and install

See [Actions](https://github.com/jappy202/vrization-iphone-build./actions) for results. Download `VRization-iPhone-build4` from a successful run and extract the IPA. Failed runs may publish diagnostics without an IPA. The device executable is checked as arm64 iOS, not Simulator. Source identity, customization checksum, build logs, original notices and IPA checksum are included.

Sign/install locally using [Sideloadly](https://sideloadly.io/) with your own Apple account. No Apple credentials or certificates are used by the workflow. For an update, use the same account and bundle settings as the existing installation. Avoid deleting the app if you want to preserve preferences. Free signing normally needs refreshing every seven days.

See [INSTALL-WINDOWS.md](INSTALL-WINDOWS.md) for initial setup. The upstream 0.5.1 Windows package needs no changes for these phone-local controls. USB and LAN are intended routes; a PC hotspot can supply a local network when campus Wi-Fi isolates peers.

Phone-based tracking is the current scope. AirPods/HeadTrack input is not integrated by this patch.
