# OpenClaw PR 132683 proof

Evidence for OpenClaw head `f16b9ab6d3fe3236e74abef649fdd9e279391958`.

- `before-after.png` — original and aligned iOS composer using the same task text.
- `controls-and-options.png` — direct footer controls and actual iOS option menus.
- `ios-composer-pr-proof.mp4` — 9-second silent H.264 proof clip, 1920x1080 at 30 fps.
- `ios-composer-pr-proof.gif` — inline PR preview, 960x540 at 12 fps.

The proof clip passed HyperFrames lint, runtime, layout, motion, and contrast checks. The iOS
transport suite passed 25 tests on the stacked delivery head containing this composer head
unchanged. The complete iOS app also compiled successfully for a generic iOS Simulator.
