# OpenClaw PR 120791 — profile identity synchronization proof

Proof for https://github.com/openclaw/openclaw/pull/120791.

Source head: `0b453e0eee`

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
e8c04a3d3fb67c4297641e1bc4cf509a48b6d53ee05b587d01efbd9786727a93  profile-identity-sync.gif
74d45d3a89273edcf6edffbe1fb31d9af80a39fff371d69fd3fca4f01fc91785  before-stale-sidebar-identity.png
f7061efef38a30cf94da465d696bd635df096f553ee8f895b1ea32390373e9b3  after-refreshed-sidebar-identity.png
```
