# OpenClaw PR 132683 authority evidence

Evidence for OpenClaw head `d1fdfd23cd8f2925fa8c5aa6f6a4afb25a168e1f`.

- `ios-client-state-migration.log` — opens a v6-shaped real SQLite client-state database with
  current code, applies migrations v7/v8, cold-reopens it, proves the legacy row survived,
  proves an older reader cannot claim the settings-bound row, authorizes retry with the current
  client, and cold-reopens again with the captured settings intact.
- `gateway-owner-boundary.log` — passes the admission CAS, broaden-after-admission freeze, and
  ACP fail-closed owner tests.

The branch also adds a QA Lab child-Gateway case in
`test/e2e/qa-lab/runtime/gateway-rpc-chat.e2e.test.ts`. It drives the real Gateway and embedded
runtime against the deterministic HTTP provider, attempts an exec write under read-only admitted
settings, verifies the sentinel file remains absent, and proves a stale-settings send reaches
neither provider nor transcript. This bundle does not claim a successful exact-head execution of
that complete QA case; the files here are the successful focused evidence only.
