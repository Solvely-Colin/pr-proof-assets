# OpenClaw PR 132683 exact-head evidence

Evidence for OpenClaw head `814e0bac9d5e872e4fc388e122b736d1feb40dab`, rebased onto
`fa6b02a14d6e25ada64d12e0c2c217df2d0b54c8`.

- `ios-composer-exact-head.mp4` records the real iOS UI-test flow on the dedicated
  OpenClaw Capture simulator.
- `ios-composer-contact-sheet.png` shows the compact composer, permission and effort
  menus, skills, connectors, tool access, and expanded draft.
- `ios-composer-ui-test.log` records
  `testChatComposerStartsCompactAndGrowsWithDraft`: 1 passed, 0 failed, 0 skipped.
  It verifies model state transitions through the composer value. Xcode 27's XCUI bridge
  does not expose native Picker menu-item selection traits, so the test does not claim a
  string value for that platform-owned trait.
- `gateway-authority.log` records stored authority retained for legacy callers, restricted
  ACP takeover rejected before hooks, and permission/tool differences rejecting steering.
- `apple-authority.log` records the local database downgrade fence, v6-to-v8 cold reopen,
  and qualified/unqualified model selection matching.

The local SQLite evidence concerns only iOS `client-state.sqlite`; no Gateway database
schema is changed.
