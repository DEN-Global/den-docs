# Owner Admin and delegated administration

## Implemented

The Owner Admin is the server-pinned Primary Super Admin identity. Owner power is never granted just because someone types a matching email address in a browser. Accounts use salted scrypt password hashes; login and sensitive administrator actions retain the existing authenticator MFA requirements.

The admin workspace now includes overview counts, the latest 200 users and orders, administrator provisioning, a role builder, verification, finance ledger oversight, the latest 100 audit events, and owner page locks. User suspension/reactivation revokes sessions and cannot target the owner or the acting administrator.

- **Owner Admin:** all supported administrator sections; only the owner can control page locks and the global International Trade lock. The owner cannot be modified through delegated admin creation or user status forms.
- **Sub Admin:** broad operational authority, except owner-only administrator creation/role management, owner-only controls and owner-locked sections. It cannot modify the owner or itself.
- **Finance Admin:** finance ledger oversight. No live payment, debit, payout or bank transfer provider has been enabled by this change.
- **Verification Admin:** organization and rider verification plus the existing warehouse review capability. Private driver's licence upload/storage workflows are not configured by this change; existing application records do not constitute document verification.
- **Custom roles:** named sets of supported capabilities created through the UI, with no source-code editing. Custom roles never mint owner or super-admin authority. International capabilities remain subject to the owner's trade activation.

Page locks apply at the server to both new console APIs and legacy administrator APIs. Non-owner administrative writes also check the lock and active session inside the audit transaction. Role edits revoke assigned sessions; assignment to an existing email preserves its password. Password fields are excluded from audit records and cleared after successful creation. Built-in role definitions are protected.

## One-time real owner setup is pending

The requested owner email is the default in the local setup command. Its password has not been embedded in source, logs, screenshots, tests or fixture data, and the real account has not been created yet.

From the backend directory, run:

```sh
npm run setup:owner -- --replace-test-owner
```

Enter the owner email (or accept the default), then enter and confirm the password in the hidden terminal prompt. The replacement flag accepts only an existing `@example.test` QA owner; it will not replace a real owner or overwrite existing credentials. This creates the real owner locally, revokes/removes the old QA administrator's authority and records the bootstrap in the audit chain. The updated local API reads this identity on each request. Sign in at `/admin/` and enable MFA in **Security**. Account creation and page locks remain MFA protected. Admin sign-in without fresh MFA opens Security first.

This does not provision the Cloudflare database or deploy code. Cloud deployment requires applying migration `0007_admin_console.sql`, deploying the updated Worker and UI artifacts, and securely pinning the real owner ID through a separate provisioning process. No remote owner account was created.

## Verification

- Backend suite: 80 tests passed, including seven console tests for permission isolation, password hashing, audit redaction, existing-password preservation, protected owner, custom roles, session revocation, lock revisions, direct API denial and stale MFA.
- Shared API/contract suite: 3 tests passed.
- Eight app builds passed before final copy/style changes; final complete build and integrity checks rerun.
- Hidden terminal owner bootstrap was exercised against an isolated temporary QA database using synthetic credentials.
- Browser inspection used a separate QA database and synthetic owner on port 8788; no real owner credential was entered. The MFA-fresh test session was seeded only in that isolated database. API tests independently verify stale MFA rejection.
- Screenshots in `verification/owner-admin` show overview, account creation, role builder and owner lock controls. They are QA data, not evidence of real-owner activation.

## Updated entry and role rules

The public directory is replaced by one neutral sign-in. New registrations automatically sign in to Consumer; members may permanently choose one additional professional role. Returning members go to their chosen role after sign-in, with Consumer always available. Administrators are routed directly to Admin; no public Admin link is shown. Only the Owner Admin may provision administrators or define administrator roles. See migration `0008_workspace_access.sql`. Backend role checks protect direct API calls; hiding links alone is not the access boundary.
