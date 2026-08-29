# OpenClaw PR 132683 authority repair evidence

Evidence for OpenClaw head `40999060d2c4e7c582ee86774026c10034351dc0`.

- `hook-authority-boundary.log` — an unhandled reply-dispatch hook attempts to recover and mutate
  the old nested admitted-settings object. The object is absent, the hook receives only a
  non-writable restrictive-policy fact, the original nested deny remains intact for default
  dispatch, ACP still fails closed, and the 16-test public ACP SDK suite passes.
- `ios-client-state-migration.log` — a v6-shaped SQLite client-state database migrates through
  v7/v8, cold-reopens, fences an older-reader claim, accepts a current-client retry, and
  cold-reopens again with the captured settings intact.
- `gateway-owner-boundary.log` — admission CAS, broaden-after-admission freeze, and ACP
  fail-closed owner tests pass.

The authority object remains private to the default runtime path. Public reply-dispatch hooks now
receive only the immutable derived fact needed by ACPX; no hook receives the nested permission or
tool policy.
