# PR #113908 exact-head Android proof

- Source SHA: `46dc3194489e47e86f86123eb7748fd788b47546`
- APK SHA-256: `89992b420e7afcd071a3fed19fdb6635df307fa26b65e528e83cab7ddc398e15`
- Installed `base.apk` SHA-256: `89992b420e7afcd071a3fed19fdb6635df307fa26b65e528e83cab7ddc398e15`
- Device: Android 16 / API 36, `sdk_gphone64_arm64`, arm64-v8a
- Gateway: isolated loopback-only local gateway, normal device and node approval flow, disposable proof token

## Media

- `onboarding-final.mp4`: clean install, normal onboarding, device approval, node approval, and connected shell.
- `navigation-layouts.mp4`: compact drawer, Android Back dismissal, system-edge ownership, medium rail, expanded permanent navigation, secondary drawer, and scrim dismissal.
- `ime-lifecycle.mp4`: Chat, IME resize, keyboard Back dismissal, and cold restart.

## What this proves

- The exact APK bytes installed on the emulator match the locally built artifact.
- The exact head pairs and connects through the normal UI and reports `Online` / `Healthy`.
- Adaptive navigation responds at compact, medium, and expanded widths.
- Drawer dismissal works with Android Back and the scrim.
- The system left-edge gesture remains owned by Android Back rather than opening the app drawer.
- Chat remains usable when the IME is shown.
- A forced cold start reconnects without a crash and opens the default Overview destination.
- A true background-process kill followed by saved-task restoration crashes in the same unchanged reader-state code on both the PR head and its recorded base. See `process-restoration-baseline.txt`.

## Limits

- Resize coverage is emulator window resizing, not a physical foldable hinge/tabletop device.
- This does not prove TalkBack spoken output, Switch Access traversal, predictive-back animation frames, RTL rendering, reduced motion, or physical-device gesture arbitration.
- True saved-task process restoration is not proven. Both the PR head and base crash in unchanged `ChatReaderScrollController` code, so the defect is a pre-existing Android baseline issue rather than a regression introduced by this PR.
