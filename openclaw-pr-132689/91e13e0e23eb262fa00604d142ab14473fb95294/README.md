# OpenClaw PR 132689 current-main manifest

Final stacked OpenClaw head `91e13e0e23eb262fa00604d142ab14473fb95294` is based on
parent `bd34f56c8d4e874efeb78d51d50faf6a786e3a80`.

The full runtime and macOS integration proof is linked from
`openclaw-pr-132689/89f8bd4cb1fbff214857bbcc85db5357fd4fb4dc`.
At this final head, the route-lease owner refuses a settings-bound queued send before any
transport dispatch when the Gateway lacks settings CAS.

`final-head-validation.log` records the exact regression, native i18n, and diff checks.
Swift lint reports 0 violations across the app surfaces.
