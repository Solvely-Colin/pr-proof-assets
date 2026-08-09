# OpenClaw PR 120791 — profile identity synchronization proof

Proof for https://github.com/openclaw/openclaw/pull/120791.

Source head: `e1d1f43cca`

## Scenario

The Control UI begins with **Test Person** in the bottom-left identity card. A revisioned presence event then updates the authenticated profile, and the sidebar changes in place to **Updated Person** without a reload or flash back to stale identity data.

The focused browser test also verifies the revisioned avatar URL and the avatar-removal fallback.

## Artifacts

- `profile-identity-sync.gif`: motion proof of the live sidebar identity update.
- `before-stale-sidebar-identity.png`: sidebar before the profile refresh.
- `after-refreshed-sidebar-identity.png`: sidebar after the profile refresh.

## Validation

```text
PASS focused gateway + UI unit suite — 5 files, 321 tests
PASS profile page UI E2E proof — 1 file, 4 tests
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
ae02bf07e9e66e50b671b68b1ce61e642099f6d960bd6201952b3ba4511a6d07  profile-identity-sync.gif
3044a6675c1b94dd11d3ec5164eb7a22ebebbfa497a6dc4877a2e8d8d0d58c35  before-stale-sidebar-identity.png
1d40c9bb461bbc2b075d57fc37db34d123c092254bf531f0584954296dc97703  after-refreshed-sidebar-identity.png
```
