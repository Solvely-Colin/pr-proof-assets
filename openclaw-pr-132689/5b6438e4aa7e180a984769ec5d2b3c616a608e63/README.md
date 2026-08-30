# OpenClaw PR 132689 exact-head evidence

Evidence for stacked OpenClaw head
`5b6438e4aa7e180a984769ec5d2b3c616a608e63` on parent
`d3b9960d73d893b4d7ad364a5e60f5160637961c`.

`exact-head-validation.log` records:

- native localization inventory verification with 4,406 entries and no drift;
- candidate-to-older-reader-to-candidate client database reopen and claim fencing;
- old-Gateway structured replay parking terminally without a retry or health loop;
- a full generic iOS Simulator build, including the shared kit, app, extensions, and
  Watch app, ending in `BUILD SUCCEEDED`.

The log is redacted for local machine paths. It exercises the real GRDB migration and
outbox owners while using deterministic transport fixtures; it is not presented as a
live external-provider run.
