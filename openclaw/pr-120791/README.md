# OpenClaw PR 120791 — profile identity synchronization proof

Proof for https://github.com/openclaw/openclaw/pull/120791.

Source head: `7e6953ae14`

## Scenario

The Control UI begins with **Test Person** in the bottom-left identity card. A revisioned presence event then updates the authenticated profile, and the sidebar changes in place to **Updated Person** without a reload or flash back to stale identity data.

The focused browser test also verifies the revisioned avatar URL and the avatar-removal fallback.

## Artifacts

- `profile-identity-sync.gif`: motion proof of the live sidebar identity update.
- `before-stale-sidebar-identity.png`: sidebar before the profile refresh.
- `after-refreshed-sidebar-identity.png`: sidebar after the profile refresh.

## Validation

```text
PASS focused gateway + UI unit suite — 5 files, 280 tests
PASS profile page UI E2E proof — 1 file, 3 tests
PASS core TypeScript check
PASS core-test TypeScript check
PASS pnpm ui:build
PASS oxfmt --check (changed files)
PASS git diff --check
PASS TruffleHog secret scan
PASS autoreview — no accepted/actionable findings
```

## SHA-256

```text
f7cd2427c78f3c081c5248c9b1da8dec68a94e4e3fa8792b803e7ab9ae60dbb5  profile-identity-sync.gif
901fca10ac6bf9300ac103580b796037cec63955711be70d42beb385942cfc69  before-stale-sidebar-identity.png
f14b2119db671c7c7c3d7ba82da54501035fdcd0ed56c18cdef4ad95c28964f7  after-refreshed-sidebar-identity.png
```
