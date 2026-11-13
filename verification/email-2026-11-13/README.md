# Supabase signup email activation — 13 November 2026

Gmail SMTP test returned HTTP 200; the owner confirmed receipt in Gmail. Production-only SUPABASE_URL and SUPABASE_ANON_KEY were configured in Vercel using the publishable key, never a service-role key. No credentials were committed.

Redeployed the unchanged black-green-release source: dpl_83aTVCpa7JXK8TJBuhEGWjKsdbb5, READY. Live /api/auth/options reports emailCodes=true, registrationEmail=true, passwordReset=false. Browser review confirms the enabled Send verification code button and verification instructions.

The deployed adapter passed isolated checks for OTP request payload, verification payload, malformed/rejected tokens and upstream throttling. An actual new-account signup, received code submission and login still require the owner to enter private credentials/code in the app. These have not yet been verified end to end. Password recovery remains separately disabled.
