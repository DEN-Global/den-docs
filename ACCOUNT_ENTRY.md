# Public entry and permanent role choice

The public `/` entry redirects to the neutral DEN sign-in. It no longer lists role workspaces or an Admin link. The same sign-in authenticates all account types; authority comes from trusted server records, never from a claimed email or selected browser route.

New public registrations automatically sign in and land in Consumer. A member may choose one additional role: Manager, Rider, Dispatch, Transport, Shipment or Warehouse. The role choice is permanent, including database triggers preventing changes/deletion. Consumer stays available. This does not grant business, rider, driver or facility approval.

After selection, the UI shows only Consumer and the chosen role. Other role URLs redirect to Consumer, and protected APIs enforce the choice independently of the UI. Returning member sign-ins route to the chosen role. Administrators route directly to `/admin/`; without fresh MFA, Security opens first. Admins do not receive the public role chooser.

Administrator creation and admin role management are now Owner Admin only. Sub Admin access to new and legacy provisioning endpoints is denied. Public registration cannot create administrators, and typing an Admin URL cannot grant privileges. The existing one-time real-owner setup remains pending; no supplied owner password was stored or used in QA.

## Validation

- Backend: 85 tests passed, including five new tests for Consumer-only start, rejecting Admin selection, immutable choice, direct role API denial, racing selections and owner-only provisioning.
- Browser on an isolated QA database: verified public sign-in, Consumer start with no role directory, one-time Manager selection, only Consumer/Manager links, Rider URL returning to Consumer, and owner sign-in routing to Admin with the MFA gate.
- The main local `/` page was opened and verified to show sign-in. Screenshots in `verification/account-entry` contain empty forms or synthetic QA identities only.
- All eight app builds and shared snapshot checks pass. Cloudflare deployment is unchanged. Migration `0008_workspace_access.sql` is required before deploying the updated backend.

Existing members have no inferred professional role by default; they must explicitly choose one on their next Consumer visit. Existing business or rider records are preserved and existing verification rules still apply. This deliberately does not silently assign privileges from historical records.
