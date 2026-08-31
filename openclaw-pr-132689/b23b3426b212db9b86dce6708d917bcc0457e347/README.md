# PR #132689 exact-head proof

- PR head: `b23b3426b212db9b86dce6708d917bcc0457e347`
- Media capture source head: `33ad964324f86301a60a060ab9435f05d51c11a7`
- Stacked parent: `48b172c027161e17beb81f6621072e42669b71a8`
- Device: dedicated `OpenClaw Capture` iPhone simulator, iOS 27.0
- Captured: 2026-08-31

## Visual proof

`durable-followup.mp4` is a fresh 20-second simulator capture of the behavior owned by this PR: a first message starts an active response, a second follow-up is composed while Stop remains active, and the follow-up is accepted without degrading into an unstructured resend. The final restack preserves byte-identical `apps/ios` (`7b7716fc8a916c13ddcea035c8fa69b92c6d0527`) and `apps/shared/OpenClawKit` (`efb806a93ae6e12b0473cd508aa4a0b7229efb52`) trees.

- `followup-ready.png` shows the second follow-up ready to send during the active response.
- `followup-sent.png` shows the follow-up accepted while the response remains active.

No parent-only styling footage is used as the primary evidence for this child PR.

## Executed proof

- `OpenClawSnapshotUITests/testActiveResponseComposerMorphsFromStopToFollowUp`: 1 passed, 0 failed. See `ui-test.log`.
- Generic iOS Simulator build: passed. See `ios-build.log`.
- Final-head Gateway chat/admission/session suites: 87 passed, 0 failed.
- Route-lease settings-CAS regression: passed.
- `ChatTranscriptCacheStoreTests`: 62 passed, 0 failed.
- Native i18n: 4,406 entries passed.
- Repository formatter: passed across 31,978 files.
- Bounded Codex autoreview: 0 actionable P0 findings in one complete pass.

The retained logs cover the captured iOS tree. Final-head formatter, i18n, Gateway/session, reply-dispatch, and Codex-review gates were rerun after the mechanical restack. The macOS Xcode 27 local build reaches the unrelated current-main `quinaryLabelColor` rename; hosted CI uses Xcode 26.6.
