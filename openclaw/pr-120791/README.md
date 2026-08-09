# OpenClaw PR 120791 — profile identity synchronization proof

Proof for https://github.com/openclaw/openclaw/pull/120791.

Source head: `faf257250c`

## Scenario

The Control UI begins with **Test Person** in the bottom-left identity card. A revisioned presence event then updates the authenticated profile, and the sidebar changes in place to **Updated Person** without a reload or flash back to stale identity data.

The focused browser test also verifies the revisioned avatar URL and the avatar-removal fallback.

## Artifacts

- `profile-identity-sync.gif`: motion proof of the live sidebar identity update.
- `before-stale-sidebar-identity.png`: sidebar before the profile refresh.
- `after-refreshed-sidebar-identity.png`: sidebar after the profile refresh.

## Validation

```text
PASS focused gateway + UI unit suite — 8 files, 446 tests
PASS profile page UI E2E proof — 1 file, 4 tests
BLOCKED full core/core-test TypeScript checks — current-main failures outside changed files
PASS pnpm ui:build
PASS oxfmt --check (changed files)
PASS git diff --check
PASS TruffleHog secret scan
PASS autoreview — no accepted/actionable findings
```

## SHA-256

```text
9dbcaeb5f984d86015820e940630a90c2ba6025bbb61d9570d647d508f9c89c3  profile-identity-sync.gif
58d4ec8e067da14f6da4a9696f4e7844d223472bd6d397c728079e816dde2ba2  before-stale-sidebar-identity.png
0375742301d9d2ff1f54b05ac44400e993e1b7a81a32b02bdd58b940eadae13a  after-refreshed-sidebar-identity.png
```
