# OpenClaw PR 132689 final-head manifest

Final stacked OpenClaw head: `89f8bd4cb1fbff214857bbcc85db5357fd4fb4dc` on
parent `15661d458ee8695aa51fe47c1b864317cd55d38b`.

The full iOS build, migration, composer parity, and macOS integration proof remain in the
[runtime bundle](../88ec1aae7e88087a611167db07f8423d9b106341/README.md).

The final security invariant is owned by `OpenClawChatTransportRouteLease`: a queued send
with captured permission/tool settings cannot invoke any transport closure unless that
lease advertises settings CAS. `final-head-validation.log` records the regression passing,
plus native i18n, the full unused-export guard, and diff checks.

SQLite remains local to iOS `client-state.sqlite`; there is no Gateway SQL/schema or
protocol-version change.
