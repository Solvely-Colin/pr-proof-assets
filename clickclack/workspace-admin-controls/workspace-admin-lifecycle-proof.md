# ClickClack Workspace Admin Lifecycle Proof

Date: 2026-07-12

PR: https://github.com/openclaw/clickclack/pull/54

Branch: `s/workspace-admin-controls`

## Redacted Behavior Coverage

- Second-member icon visibility: `TestWorkspaceAdminHTTPUploadLifecycle` uploads an `image/png` icon as the owner, saves `/api/uploads/<redacted-upload-id>` as `workspace.icon_url`, then fetches the same URL as a second workspace member and verifies the response body.
- Non-owner and bot rejection: the same HTTP test verifies member `PATCH /api/workspaces/<redacted-workspace-id>` is `403`, bot-token `PATCH /api/workspaces/<redacted-workspace-id>` is `403`, and member transfer before ownership is `403`.
- Transfer: the owner transfers workspace ownership to the second member and the test verifies `workspace.ownership_transferred`.
- Deletion cleanup: after transfer, old owner delete is `403`; new owner delete is `204`; the test checks the local upload object's storage path existed before deletion and is removed afterward.
- Audit traceability: the update audit log entry is checked for `metadata.icon_url == /api/uploads/<redacted-upload-id>`.

## Upgrade Coverage

- SQLite: `TestWorkspaceIconMigrationUpgradesExistingData` applies migrations before `0021_workspace_icon_url.sql`, inserts a pre-existing workspace, runs `Migrate`, and verifies `Workspace.IconURL` defaults to empty.
- Postgres: `TestWorkspaceIconMigrationUpgradesExistingData` applies migrations before `0014_workspace_icon_url.sql`, inserts a pre-existing workspace, runs `Migrate`, and verifies `Workspace.IconURL` defaults to empty. Local run skipped because `CLICKCLACK_POSTGRES_TEST_DSN` is not configured.

## Commands Run

```text
pnpm generate:sqlc
PASS: sqlc regenerated SQLite/Postgres generated query output.

go test ./apps/api/internal/httpapi -run TestWorkspaceAdminHTTPUploadLifecycle -count=1 -v
PASS: second member icon GET, rejection matrix, transfer, delete cleanup, audit metadata.

go test ./apps/api/internal/store/sqlite -run TestWorkspaceIconMigrationUpgradesExistingData -count=1 -v
PASS: SQLite upgrade from pre-icon schema.

go test ./apps/api/internal/store/postgres -run TestWorkspaceIconMigrationUpgradesExistingData -count=1 -v
SKIP locally: set CLICKCLACK_POSTGRES_TEST_DSN to run Postgres integration smoke.

go test ./apps/api/internal/httpapi ./apps/api/internal/store/sqlite ./apps/api/internal/store/postgres
PASS: affected API, SQLite store, and Postgres store package tests.

pnpm typecheck
PASS.

pnpm --filter @clickclack/web typecheck
PASS.

pnpm build
PASS: regenerated web build and embedded webassets.
```

## Screenshot

![Workspace icon proof](https://raw.githubusercontent.com/Solvely-Colin/pr-proof-assets/34875f5c494d3250f83f7a29a38f4c4e1b28aaa3/clickclack/workspace-admin-controls/workspace-icon-proof.png)
