# OpenClaw PR #121087 visual proof

- Source PR: https://github.com/openclaw/openclaw/pull/121087
- Reviewed head: `d4c742f17926c012764022a8aee6dd8d905e4c71`
- Viewport: 1440 × 900, dark mode
- Product surface: built Control UI served by the repository E2E server
- Backend: deterministic mocked Gateway; the rendered UI and text-size interaction are the real product

## Scenario

1. Open Settings → Appearance at the default 100% text size.
2. Hold the initial state for inspection.
3. Select 140% at normal interaction speed.
4. Hold the final state so the enlarged settings sidebar can be reviewed.

The recording is 11.84 seconds (approximately 12 seconds) and is not accelerated.

The media was retained across this conflict-resolution rebase because the demonstrated Settings
sidebar interaction and resolved production text-scaling behavior are unchanged. The rewritten
head preserves current-main project-header and shortcut typography, drops stale custom-icon-picker
CSS and fixture coverage after that feature's removal on main, and revalidates the live remaining
surfaces with focused browser tests, the full UI suite, and the production build.

## Capture

```bash
OPENCLAW_UI_PROOF_DIR=<proof-directory> pnpm exec vitest run ui/src/e2e/sidebar-text-scale-proof.e2e.test.ts --config test/vitest/vitest.ui-e2e.config.ts
ffmpeg -i <playwright-webm> -c:v libx264 -preset medium -crf 22 -pix_fmt yuv420p sidebar-text-scale-demo.mp4
ffmpeg -i <playwright-webm> -filter_complex "fps=10,scale=1200:-1:flags=lanczos,split[s0][s1];[s0]palettegen=max_colors=128[p];[s1][p]paletteuse=dither=bayer" sidebar-text-scale-demo.gif
```

The proof-only E2E test was removed after capture and is not part of the source PR.
