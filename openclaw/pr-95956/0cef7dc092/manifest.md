# OpenClaw PR 95956 exact-head proof after documentation update

- PR head: `0cef7dc092e3723bb3a282535d4f36c88dc88f6b`
- Main base: `29a7654b299f395da8716eb326d1b4d27005dc4d`
- Exact-head browser run: `run_be30da9afa90`
- Sanitized backend: direct AWS Crabbox `cbx_8bb8a3e73363`, public network, no Tailscale, no instance profile
- Browser fixture: `ui/public/apple-touch-icon.png`, 5,920 bytes, `image/png`
- Unsupported fixture: `unsupported-binary.bmp`, 4,096 bytes, `image/bmp`
- Browser result: 2 Chromium tests passed; required WebM, supported-PNG, and unsupported-BMP artifacts collected
- Documentation result: `docs/web/control-ui.md` now states that inline binary image previews are limited to supported images no larger than 256 KiB

The GIF and WebM are derived from the exact-head Chromium artifact. Screenshots are the supported PNG and unsupported binary fallback states captured by that same run. The UI uses synthetic `/workspace` paths only.
