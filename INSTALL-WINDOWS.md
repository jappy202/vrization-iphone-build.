# First installation on Windows and iPhone

This guide is for the experimental phone-tracking setup. AirPods/HeadTrack is a later integration.

## 1. Get the two apps

- iPhone: download the `VRization-iPhone-unsigned` artifact ZIP from a successful [build](https://github.com/jappy202/vrization-iphone-build./actions). Extract `VRization-SteamVR-unsigned.ipa`.
- Windows: download `VRization-SteamVR-Windows-x64.zip` from [upstream 0.5.1 preview](https://github.com/LexZeon/VRization/releases/tag/v0.5.1-steamvr-preview). Extract the entire ZIP into a permanent folder. Preserve its subfolders and license files; do not run from inside the ZIP.

The cloud source commit differs from the upstream release commit only in documentation. Phone app and Windows host code therefore match that release. Successful compilation is not a physical-device compatibility claim.

## 2. Sign and install the iPhone app

Install Sideloadly from https://sideloadly.io/ on Windows. Connect the unlocked iPhone with a data cable, approve Trust if prompted, and confirm Apple Devices recognizes it. Select the phone and the extracted IPA in Sideloadly and follow its signing flow with your own Apple account. Enter credentials yourself in Sideloadly, never in a repository or chat. A paid developer account is not required for ordinary personal free signing, but free signing normally expires after seven days and must be refreshed.

If iOS requests developer trust or Developer Mode, follow the phone's on-screen prompts. Developer Mode may require a restart. If signing fails, retain the exact error (exclude passwords, codes and other secrets). This particular IPA and iOS combination have not been physically tested yet.

## 3. Test the connection before starting a game

1. Keep the phone connected by USB, unlocked, with **VRization SteamVR Experimental** open in the foreground. Start in USB mode. This avoids relying on school Wi-Fi device discovery.
2. Run `Start-SteamVR-Preview.bat` from the extracted Windows folder.
3. Select the **Phone HMD** route. Follow the launcher's explicit actions to register its own SteamVR driver and open SteamVR. Keep the host folder at the same path after registration.
4. Connect/start streaming. If the host reports paused tracking, select **Resume HMD tracking on PC**. Opening the fit editor or pressing F8 can pause tracking again.
5. Verify that SteamVR recognizes a headset, the phone receives two eye views, and rotating the phone changes the view. Double-tap/recenter while facing forward if needed.
6. Only after these work, try War Thunder's VR mode. Keyboard/controller controls remain on the PC. The current route supplies rotational tracking, not room-scale position or tracked controllers.

If blocked, report which of the following is failing: app installation, USB recognition, host connection, headset recognition, visible stereo frames, or rotation tracking. Include the exact error/status from the phone and Windows host. A waiting screen alone does not show which layer failed.

## Expected use after setup

Connect USB, open the phone app, launch the Windows host and SteamVR, then start the game. Software or hardware faults may require fixes before this becomes reliable. Audio remains on the PC. Do not expect the working AirPods/HeadTrack input to control this driver automatically.
