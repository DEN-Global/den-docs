# Full sign-in background and password recovery

Applied the user's item-animation reference across the full shared sign-in background, with transparent form surroundings, readable field surfaces and retained pause/reduced-motion support. Added Forgot password, email request, six-digit code and new-password form, success message and return to sign-in.

Recovery codes are purpose-separated from registration codes, hashed, single-use, expire after ten minutes and allow five attempts. Request/verification routes enforce origin and IP/account rate limits. Reset revokes sessions and preserves MFA. Unknown accounts receive a generic response. Delivery currently requires the existing injected sender or Resend configuration; Supabase OTP is intentionally not treated as a purpose-bound password reset token for DEN's separate password store. Live recovery remains unavailable until a sender is configured.

Validation: all nine frontend builds passed. Four focused recovery tests passed, covering password replacement, session revocation, MFA retention, replay, expiry, registration-token rejection, exhausted attempts, origin, readiness, password policy and generic responses. Broader API suite: 13 pass / 2 fail; the failures are existing registration tests expecting 201 without configured verification email, while the API correctly returns 503. No production password or account changes were performed.

Browser inspected the recovery form and unavailable state before the workspace restart. The final opacity adjustment was compiled after that inspection. Further final screenshot verification was blocked by the browser policy on a stale browser error page; no bypass was attempted.

Recovered the exact previous production snapshot after temporary files were cleared; all 28 backend/config hashes matched its manifest. Packaging overlays the nine frontend builds and changes only src/app.js plus the new src/password-reset.js in the API. No unrelated local backend changes are included.

Published production deployment `dpl_Bwyz7mXBxN1MMFAgb3sCGouTxsxY`, aliased to https://den-global.vercel.app. Postdeployment checks verified all nine HTML entry pages plus API health and authentication options. Password-reset availability remains false until email sending is configured.
