# PR #132683 exact-head proof

- PR head: `878ca8fbfc20db52d1bebb9b2be1105222b75945`
- Current-main baseline: `a7be8e5ec6ff9b4169eabe3bf37bb36396ac79ad`
- Device: dedicated `OpenClaw Capture` iPhone simulator, iOS 27.0
- Captured: 2026-08-31

## Visual proof

`composer-before-after-overview.png` and `composer-before-after-closeup.png` are fresh side-by-side composites from two independently built UI-test runs. Left is current `main`; right is this exact PR head. The close-up makes the composer-only delta visible without shrinking the control row.

`composer-before-after.mp4` is a fresh 20-second side-by-side simulator capture. Left exercises the current-main composer. Right exercises the exact-head permissions, model, effort, capabilities, attachments, compact, and expanded states. Playback is accelerated only to remove UI-test waits; no UI frames were invented or substituted.

The individual source screenshots are retained alongside the composites:

- `current-main-compact.png`
- `pr-inline-controls.png`
- `pr-permissions-menu.png`
- `pr-model-menu.png`
- `pr-effort-menu.png`
- `pr-expanded.png`

## Executed proof

- `OpenClawSnapshotUITests/testChatComposerStartsCompactAndGrowsWithDraft`: 1 passed, 0 failed on the exact PR head. See `ui-test.log`.
- Generic iOS Simulator build: passed on the exact PR head. See `ios-build.log`.
- Gateway chat/admission focused suites: 69 passed, 0 failed.
- Reply-dispatch authority scope suite: 8 passed, 0 failed.
- Messaging typecheck: passed.
- Native i18n: 4,397 entries passed.

The current-main screenshots came from the same named UI test built in an isolated detached worktree at the baseline SHA. The PR screenshots and video came from the exact head above.
