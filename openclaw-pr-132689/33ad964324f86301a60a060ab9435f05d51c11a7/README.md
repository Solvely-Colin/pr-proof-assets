# PR #132689 exact-head proof

- PR head: `33ad964324f86301a60a060ab9435f05d51c11a7`
- Stacked parent: `878ca8fbfc20db52d1bebb9b2be1105222b75945`
- Device: dedicated `OpenClaw Capture` iPhone simulator, iOS 27.0
- Captured: 2026-08-31

## Visual proof

`durable-followup.mp4` is a fresh 20-second exact-head simulator capture of the behavior owned by this PR: a first message starts an active response, a second follow-up is composed while Stop remains active, and the follow-up is accepted without degrading into an unstructured resend.

- `followup-ready.png` shows the second follow-up ready to send during the active response.
- `followup-sent.png` shows the follow-up accepted while the response remains active.

No parent-only styling footage is used as the primary evidence for this child PR.

## Executed proof

- `OpenClawSnapshotUITests/testActiveResponseComposerMorphsFromStopToFollowUp`: 1 passed, 0 failed. See `ui-test.log`.
- Generic iOS Simulator build: passed. See `ios-build.log`.
- Gateway chat/admission focused suites: 69 passed, 0 failed.
- Route-lease settings-CAS regression: passed.
- `ChatTranscriptCacheStoreTests`: 62 passed, 0 failed.
- Messaging typecheck: passed.
- Native i18n: 4,406 entries passed.

`focused-validation.log` retains the bounded exact-head validation output. The macOS Xcode 27 local build reaches the unrelated current-main `quinaryLabelColor` rename; hosted CI uses Xcode 26.6.
