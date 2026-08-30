# OpenClaw PR 132689 final-head evidence

Evidence for stacked OpenClaw head
`88ec1aae7e88087a611167db07f8423d9b106341` on parent
`eb19e297d4ab35a82dc8b9aeffa0dc5f9ad8c0c6`.

- Runtime proof covers exact messaging typecheck, the localized settings-conflict
  regression, a generic iOS Simulator build, 20 composer parity cases, 62 client
  database/outbox cases, legacy NULL settings fencing, pre-v7 reopen, and older-Gateway
  structured replay parking.
- The final commit adapts the macOS transport consumer to the canonical context lease.
  It preserves settings CAS and explicitly rejects structured replay, matching the
  transport's advertised capability instead of silently degrading the message.
- `macos-build-boundary.log` shows that this caller now compiles. The local Xcode 27 build
  proceeds until an unrelated current-main `quinaryLabelColor` rename in
  `DashboardLinkBrowserTabBar.swift`; hosted CI uses Xcode 26.6 and previously reached the
  now-repaired WebChat caller error.

The SQLite work remains local to iOS `client-state.sqlite`; it does not change Gateway SQL,
the Gateway database schema, or a protocol version.
