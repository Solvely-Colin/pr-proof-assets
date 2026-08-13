# OpenClaw PR 122892 visual proof

- Source PR: https://github.com/openclaw/openclaw/pull/122892
- Exact head: `820ce56a6ef20096a29150a05cef4c8fec962832`
- Scenario: model setup device-code OAuth step with a long authorization URL and a failed authoritative refresh.
- Environment: real Control UI in Chromium, mocked Gateway WebSocket responses, 1280×900 viewport.

## Captures

- `oauth-modal-fixed-flow.gif`: normal-paced sign-in interaction with an initial pause, the complete pairing transition, and an inspectable final state.
- `before.png`: `origin/main` at `2ce420091e136da4c83e65071c6caea68f3b1ac1`, using the same long OAuth URL fixture. The content grid overflows the modal and clips actions.
- `after.png`: reviewed PR head. The URL wraps, the sign-in action stays compact, and Cancel shares the action row with Continue.

## Capture commands

```sh
OPENCLAW_UI_E2E_ARTIFACT_DIR=.artifacts/oauth-modal-fix \
  node scripts/run-vitest.mjs run \
  --config test/vitest/vitest.ui-e2e.config.ts \
  --configLoader runner \
  ui/src/e2e/model-setup.e2e.test.ts

ffmpeg -ss 0.20 -i .artifacts/oauth-modal-fix/page@6855feea42d3878ed15dcb4cbb5876d0.webm \
  -vf "setpts=4*PTS,tpad=start_mode=clone:start_duration=2:stop_mode=clone:stop_duration=3,fps=10,scale=960:-1:flags=lanczos" \
  oauth-modal-fixed-flow.gif
```

The OAuth URL is deterministic test data; no account credentials or live auth session are present.
