# OpenClaw PR 95956 final exact-head proof

- PR head: `b0892aa41f9c428fc5bbb3bfc43645239529539d`
- Main base: `29a7654b299f395da8716eb326d1b4d27005dc4d`
- Exact-head focused and browser run: `run_18c64e9a96c4`
- Sanitized backend: direct AWS Crabbox `cbx_c12a8724885d`, public network, no Tailscale, no instance profile
- Browser fixture: `ui/public/apple-touch-icon.png`, 5,920 bytes, `image/png`
- Unsupported fixture: `unsupported-binary.bmp`, 4,096 bytes, `image/bmp`
- CI regression result: `pnpm check:architecture`, `pnpm native:i18n:check`, `pnpm android:i18n:check`, and `pnpm apple:i18n:check` passed
- Focused result: 68 gateway tests and 24 Control UI tests passed
- Client/protocol result: protocol regeneration, UI type checks, and focused E2E lint passed
- Swift API result: the refreshed `OpenClawProtocol` target built, then an `AgentsWorkspaceFile` caller with `encoding: AnyCodable` typechecked against that module
- Browser result: 2 Chromium tests passed; required WebM, supported-PNG, and unsupported-BMP artifacts collected

The GIF and WebM are derived from the final exact-head Chromium artifact. Screenshots are the supported PNG and unsupported binary fallback states captured by that same run. The UI uses synthetic `/workspace` paths only.
