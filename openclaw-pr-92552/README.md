# PR 92552 iOS foreground reconnect proof

- before-connected-lifecycle.gif: baseline healthy lifecycle recording
- after-connected-lifecycle.gif: patched healthy lifecycle recording
- forced-stale-baseline.gif: forced gateway-down simulator attempt; simulator recovered, so this is not a before/after delta
- *.sanitized.log: redacted simulator/gateway logs
