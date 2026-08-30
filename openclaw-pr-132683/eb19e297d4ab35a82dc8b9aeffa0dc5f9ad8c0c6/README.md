# OpenClaw PR 132683 final-head evidence

Evidence for OpenClaw head `eb19e297d4ab35a82dc8b9aeffa0dc5f9ad8c0c6`, rebased onto
`fa6b02a14d6e25ada64d12e0c2c217df2d0b54c8`.

- `ios-composer-exact-head.mp4`, its contact sheet, UI log, and authority log were
  captured at runtime-equivalent head `f29f0a561a7574687e2123208e29816f146fe437`.
- The only later commit refreshes generated native-i18n inventory and makes a module-local
  constant non-exported; it does not change runtime behavior or the built UI.
- `final-head-validation.log` proves native i18n (4,397 entries), the full unused-export
  guard, SQLite session-schema baseline, and diff checks at the final head.
- The real iOS UI flow passes 1/1 and covers permissions, model switching, effort, context,
  attachments, skills, connectors, tool access, and compact/expanded states.
- Authority evidence includes 210 dispatch tests, 20 composer parity tests, and 59 client
  database/outbox tests.

The local SQLite evidence concerns only iOS `client-state.sqlite`; no Gateway database
schema is changed.
