# PR #132683 exact-head proof

- PR head: `48b172c027161e17beb81f6621072e42669b71a8`
- Media capture source head: `878ca8fbfc20db52d1bebb9b2be1105222b75945`
- Current-main baseline: `a7be8e5ec6ff9b4169eabe3bf37bb36396ac79ad`
- Device: dedicated `OpenClaw Capture` iPhone simulator, iOS 27.0
- Captured: 2026-08-31

## Visual proof

`composer-before-after-overview.png` and `composer-before-after-closeup.png` are fresh side-by-side composites from two independently built UI-test runs. Left is the recorded `main` baseline; right is the captured PR head. The final PR head changes only TypeScript import ordering: its `apps/ios` tree (`952e7e89e50c491082ec0d964215b166b8fdf76a`) and `apps/shared/OpenClawKit` tree (`484f542bd2a8a8a411418ff144e5f0e6361151fd`) are byte-identical to the capture source head.

`composer-before-after.mp4` is a fresh 20-second side-by-side simulator capture. Left exercises the baseline composer. Right exercises permissions, model, effort, capabilities, attachments, compact, and expanded states. Playback is accelerated only to remove UI-test waits; no UI frames were invented or substituted.

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
- Final-head Gateway chat/admission/session suites: 87 passed, 0 failed.
- Reply-dispatch authority scope suite: 8 passed, 0 failed.
- Native i18n: 4,397 entries passed.
- Repository formatter: passed across 31,978 files.
- Bounded Codex autoreview: 0 actionable P0 findings across two complete chunks.

The baseline screenshots came from the same named UI test built in an isolated detached worktree. The PR media came from the byte-identical iOS source trees named above; final-head TypeScript gates and focused runtime tests were rerun after the formatter-only commit.
