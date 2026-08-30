# OpenClaw PR 132683 exact-head evidence

Evidence for OpenClaw head `d3b9960d73d893b4d7ad364a5e60f5160637961c`, rebased onto
`fa6b02a14d6e25ada64d12e0c2c217df2d0b54c8`.

- `ios-composer-exact-head.mp4` records the real iOS UI test flow on the dedicated
  OpenClaw Capture simulator.
- `ios-composer-contact-sheet.png` shows the compact composer, direct footer controls,
  Plus menu, connectors, skills, and tool-access states from that recording.
- `ios-composer-ui-test.log` records
  `testChatComposerStartsCompactAndGrowsWithDraft`: 1 passed, 0 failed, 0 skipped.
  The build exports the exact OpenClaw SHA in the log.
- `ios-client-state-migration.log` records a v6-shaped local client database migrating
  through v7/v8, cold reopening, and fencing an older-reader claim before a current retry.
- `gateway-owner-boundary.log` records three focused owner-boundary checks: stale
  settings rejected at Gateway admission, authority kept private from reply hooks, and
  restrictive ACP dispatch stopped before `runTurn`.

The bundle makes no new claim about Gateway SQL. The persistence proof concerns only the
iOS local `client-state.sqlite` database.
