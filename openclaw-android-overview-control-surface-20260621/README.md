# OpenClaw Android Overview Control Surface Proof

Code branch: `codex/android-overview-control-surface`
Code SHA: `a2c9e2f41c`
Base SHA: `5693fcda78`
Captured: 2026-06-21

## Fresh App Proof

- `fresh/all-tabs-contact-sheet.png` - current emulator stills for Overview, Chat, Voice, and Settings.
- `fresh/openclaw-pr-proof.gif` - short real-app tab walk.
- `fresh/openclaw-pr-proof.mp4` - source recording for the GIF.
- `fresh/01-overview.png` through `fresh/04-settings.png` - full-size current tab stills.

## Before / After Context

- `before-after/all-tabs-before-after.png` - combined before/after comparison sheet.
- `before-after/01-home-before-after.png`
- `before-after/02-chat-before-after.png`
- `before-after/03-voice-before-after.png`
- `before-after/04-settings-before-after.png`

## Validation Logs

Green after rebase onto `origin/main`:

- `logs/rebased-git-diff-check.log`
- `logs/rebased-gradle-ktlint-check.log`
- `logs/rebased-gradle-shellscreen-test.log`
- `logs/rebased-gradle-assemble-play-debug.log`

Captured known blocker:

- `logs/gradle-lint-play-debug.log`
- `logs/lint-errors-summary.log`

`./gradlew :app:lintPlayDebug` still fails on existing Android lint debt outside this UI slice:
`READ_EXTERNAL_STORAGE` in `app/src/play/AndroidManifest.xml`, notification API guard in `OnboardingFlow.kt`,
package visibility in `DeviceHandler.kt`, `@RequiresApi` propagation in `GatewayDiscovery.kt`, and debug receiver export policy.
