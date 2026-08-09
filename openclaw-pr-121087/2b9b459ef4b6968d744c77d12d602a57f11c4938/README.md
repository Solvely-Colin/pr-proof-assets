# OpenClaw PR #121087 visual proof

- Source PR: https://github.com/openclaw/openclaw/pull/121087
- Reviewed head: `2b9b459ef4b6968d744c77d12d602a57f11c4938`
- Viewport: 1440 × 900, dark mode
- Product surface: built Control UI served by the repository E2E server
- Backend: deterministic mocked Gateway; the rendered UI and text-size interaction are the real product

## Scenario

1. Open Settings → Appearance at the default 100% text size.
2. Hold the initial state for inspection.
3. Select 140% at normal interaction speed.
4. Hold the final state so the enlarged settings sidebar can be reviewed.

The recording is 12.08 seconds and is not accelerated.

## Capture

```bash
OPENCLAW_UI_PROOF_DIR=<proof-directory> pnpm exec vitest run ui/src/e2e/sidebar-text-scale-proof.e2e.test.ts --config test/vitest/vitest.ui-e2e.config.ts
ffmpeg -i <playwright-webm> -c:v libx264 -preset medium -crf 22 -pix_fmt yuv420p sidebar-text-scale-demo.mp4
ffmpeg -i <playwright-webm> -filter_complex "fps=10,scale=1200:-1:flags=lanczos,split[s0][s1];[s0]palettegen=max_colors=128[p];[s1][p]paletteuse=dither=bayer" sidebar-text-scale-demo.gif
```

The proof-only E2E test was removed after capture and is not part of the source PR.
