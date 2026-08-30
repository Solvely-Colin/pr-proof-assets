# OpenClaw PR 132689 exact-head evidence

Evidence for stacked OpenClaw head
`8817e126c4322606668242c0c2f17bb2ec2f7ff1` on parent
`f29f0a561a7574687e2123208e29816f146fe437`.

`exact-head-validation.log` records:

- exact messaging typecheck;
- the focused settings-conflict regression test preserving the stable localized error key;
- a full generic iOS Simulator build ending in `BUILD SUCCEEDED`.

Earlier tests in this exact stack also cover 20 composer parity cases, 62 client database
and outbox cases, legacy NULL settings fencing, pre-v7 reopen, and older-Gateway structured
replay parking. The log is redacted for local paths.

The SQLite work remains local to iOS `client-state.sqlite`; it does not change Gateway SQL,
the Gateway database schema, or a protocol version.
