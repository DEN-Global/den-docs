# Consumer and Manager update — 4 November 2026

Local implementation of the user's Consumer/Manager walkthrough:

- Discover lists organization logos, names and descriptions. Opening a store loads its catalog; store search searches products. Order summary remains below Discover.
- Public registration collects phone, country and a private delivery address atomically with credentials. Older clients remain compatible; existing accounts can add destinations under Delivery map.
- Delivery map replaces the Addresses navigation entry. It polls the assigned delivery every 15 seconds and loads Google Maps only after the customer selects Load Google map. Rider OneTrack offers explicit live GPS sharing while that panel is open, throttled to 15 seconds. Closing the panel stops sharing. No simulated coordinates, traffic or ETA are presented as live.
- Community combines organization/product comments with delivered-purchase reviews. Comments are public; only reviews carry the verified-purchase label. Authors can remove their own comments through the API; moderation remains capability checked.
- Public profile supports a circular photo and public display name. Profile edits cannot change the phone supplied at signup. Images are resized in the browser and restricted to small raster data URLs server-side; SVG/remote images are not accepted.
- New organization registration activates immediately. Migration 0013 activates previously pending registrations, preserving explicit rejection and suspension. This is registration, not a verified-license claim. Rider/warehouse approval policies are unchanged.
- Managers can upload a logo, about text, optional license reference, support contact, and product photo/description. Storefront and catalog edits are owner scoped. Country is inferred from the saved destination, with a named-country fallback for older accounts.
- Wallet uses actual recorded balances/history. New ledger entries emit private transaction notifications. Browser alerts are opt-in and require the app to remain open. Login emits an in-app security alert. Live deposits, withdrawals and payments remain disabled.
- Email-code sign-in is implemented for members with authenticator MFA enabled. It replaces the password with an emailed code while retaining the authenticator; administrator password+MFA is unchanged. Codes expire after 10 minutes, are hashed, limited to five guesses and consumed once. Delivery failure invalidates the challenge. Requests are rate limited and do not disclose account existence.

## Email delivery connection still required

No real sender credentials are configured. `/api/auth/options` reports emailCodes=false and registrationEmail=false, so email-code sign-in is hidden and account creation stays disabled until a sender is configured. Configure `RESEND_API_KEY` and `SIGNIN_EMAIL_FROM` privately in the backend process (or Worker secrets) after verifying the sender domain. Never commit the key. Local dev passes these environment values through; restart after setting them. Provider contract: https://resend.com/docs/api-reference/emails/send-email .

Public signup now requires a six-digit email code before creating an account. Codes are hashed, expire after 10 minutes, allow five guesses and are consumed once. The API enforces a 12-character minimum with at least one letter and one number; the form includes an accessible show/hide password button. Migration `0016_registration_email_verification.sql` adds the challenge table.

## Verification

93 backend tests pass, including signup atomicity, activation/suspension, owner scoping, media validation, phone immutability, private preferences, public comment feed/removal, transaction alerts, email-code expiry/attempts/races/replay/admin exclusion and a successful email+authenticator login with an injected test sender. Also 3 shared tests, 5 infrastructure tests, five 20-file vendor checks and all eight app builds pass.

In-app browser checked Discover -> store catalog, manager registration form and enabled catalog controls, Delivery map empty state and public profile. A transient chunk-load failure occurred while build output was being replaced; reloading the completed build resolves it. Mobile viewport override did not match requested dimensions, so mobile QA is not claimed. Real email delivery, real GPS movement, map provider rendering for an active delivery, browser permission prompts and real-money operations were not exercised. These changes are local; Cloudflare preview has not been updated.
