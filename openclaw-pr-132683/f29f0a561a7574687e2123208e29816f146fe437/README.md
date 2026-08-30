# OpenClaw PR 132683 exact-head evidence

Evidence for OpenClaw head `f29f0a561a7574687e2123208e29816f146fe437`, rebased onto
`fa6b02a14d6e25ada64d12e0c2c217df2d0b54c8`.

- `ios-composer-exact-head.mp4` records the real iOS UI-test flow on the dedicated
  OpenClaw Capture simulator.
- `ios-composer-contact-sheet.png` shows permissions, model switching, effort, context,
  attachments, skills, connectors, tool access, and compact/expanded composer states.
- `ios-composer-ui-test.log` records
  `testChatComposerStartsCompactAndGrowsWithDraft`: 1 passed, 0 failed, 0 skipped.
- `exact-head-authority.log` records 210 dispatch tests, messaging typecheck, 20 composer
  parity tests, and 59 client database/outbox tests. Restricted admitted settings block
  both pre-dispatch and reply-dispatch takeover hooks.

The local SQLite evidence concerns only iOS `client-state.sqlite`; no Gateway database
schema is changed.
