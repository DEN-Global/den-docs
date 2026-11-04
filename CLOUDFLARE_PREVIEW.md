# DEN isolated Cloudflare preview — 2026-11-04

Preview: https://den-global-preview.lekanay2005.workers.dev

The shared Worker and eight workspaces are deployed in the owner's existing Cloudflare account on its existing Workers Free plan. An explicitly created, isolated D1 database received all six additive migrations. No local QA database was copied. A fresh encryption secret was uploaded without being committed or printed. CLI access was restricted to eight granted scopes rather than the default broad request.

## Verified remote behavior

31 smoke checks passed: portal and all eight HTML routes, content-security/nosniff headers, API health, anonymous denial, real scrypt registration/sign-in, current non-admin sessions, CSRF/origin rejection, wallet money/withdrawals disabled, ordinary-user trade denial, locked international booking, disabled remote checkout, and logout revocation. Registration and sign-in passed on the current free plan; this does not promise load capacity or production readiness. Initial remote transport failures were followed by a successful bounded-retry smoke run.

- [Exact smoke evidence](verification/cloudflare-smoke.json)
- [Deployment version and isolated database record](verification/cloudflare-deployment.json)
- [Preview portal screenshot](verification/cloudflare-preview.jpg)
- [Deployed Consumer sign-in](verification/cloudflare-consumer.jpg)
- [Infrastructure CI success](https://github.com/DEN-Global/den-infrastructure/actions/runs/41804964479)

## Trying the preview

Open Consumer and choose Create an account. This fresh preview has no automatically privileged administrator and no real business approvals. Accounts share the central session across workspaces. Actual owner administrator enrollment needs a separate secure provisioning step. Use invented test information while email ownership verification, recovery and other release gates are unfinished.

Live payments, the remote payment simulator, withdrawals and International Trade are disabled. Transport/shipment quotation requests do not create carrier bookings. The full DEN feature inventory remains in IMPLEMENTATION_TRACKER.md. No paid-plan upgrade or real-money provider operation occurred.

## Releases and rollback

The authoritative preview source/configuration is den-infrastructure. The prepared release bundles the backend source/migrations and built frontend assets; instructions in PREVIEW_PLAN.md reproduce it from sibling repositories or an isolated release directory. GitHub's automatic create-app defaults were not used for this release. Automatic GitHub-to-Cloudflare deployment is not configured.

Preserve the ignored local preview encryption-key file and the Cloudflare secret; do not rotate it without a planned MFA recovery migration. Future releases must keep the exact origin, preview D1 binding and disabled-administrator mode until secure enrollment is approved. Re-deploy the previous known-good Worker version for application rollback, preserving the D1 database and immutable history. No database reset or destructive rollback is authorized.
