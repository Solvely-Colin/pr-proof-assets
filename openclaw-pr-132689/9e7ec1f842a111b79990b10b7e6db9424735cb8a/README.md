# OpenClaw PR 132689 final-head evidence

Evidence for stacked OpenClaw head
`9e7ec1f842a111b79990b10b7e6db9424735cb8a` on parent
`eb19e297d4ab35a82dc8b9aeffa0dc5f9ad8c0c6`.

- `exact-head-validation.log` contains the runtime-equivalent pre-restack messaging
  typecheck, localized settings-conflict regression, and generic iOS Simulator build.
- The final restack changed only commit identity and absorbed the parent's generated
  native-i18n inventory refresh.
- `final-head-validation.log` proves native i18n (4,406 entries), the full unused-export
  guard, the localized settings-conflict regression, and diff checks at the final head.
- Earlier stack proof covers 20 composer parity cases, 62 client database/outbox cases,
  legacy NULL settings fencing, pre-v7 reopen, and older-Gateway structured replay parking.

The SQLite work remains local to iOS `client-state.sqlite`; it does not change Gateway SQL,
the Gateway database schema, or a protocol version.
