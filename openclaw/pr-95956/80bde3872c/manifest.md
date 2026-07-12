# OpenClaw PR 95956 refreshed exact-head proof

- PR head: `80bde3872cee58ffcc457e416776fa26aa633fcd`
- Main base: `a1c4ef189bcd079be7efc6e41483d1bf13cc4459`
- Focused protocol, client, and CI-gate run: `run_0cc23d034409`
- Exact-head browser run: `run_e623368a12d8`
- Browser fixture: `ui/public/apple-touch-icon.png`, 5,920 bytes, `image/png`
- Unsupported fixture: `unsupported-binary.bmp`, 4,096 bytes, `image/bmp`
- CI regression result: `pnpm check:architecture`, `pnpm native:i18n:check`, `pnpm android:i18n:check`, and `pnpm apple:i18n:check` passed
- Focused result: 68 gateway tests and 24 Control UI tests passed
- Client/protocol result: protocol regeneration, UI type checks, and focused E2E lint passed
- Swift API result: refreshed `OpenClawProtocol` module typechecked an `AgentsWorkspaceFile` caller with `encoding: AnyCodable`; the full package test is separately blocked by the unchanged current-main `SwiftUIMacros.StateMacro` toolchain failure in `OpenClawChatUI/ChatLinkPreview.swift`
- Browser result: 2 Chromium tests passed; required WebM, supported-PNG, and unsupported-BMP artifacts collected

The GIF and WebM are derived from the exact-head Chromium artifact. Screenshots are the supported PNG and unsupported binary fallback states captured by that same run. The UI uses synthetic `/workspace` paths only.
