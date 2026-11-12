# DEN character intro and sphere

Reference: user-provided 35-second screencast. Inspected contact sheets around the character transition and rotating sphere. Created original DEN motion: character field, DEN identity reveal, rotating 620-point typographic sphere. Intro lasts 2.6 seconds once per tab session, with skip/replay, keyboard Escape and reduced-motion support. Existing greenhouse is retained in an expandable section below the shared sign-in hero and existing pet-care placements.

Nine frontend builds passed. Browser verified sphere rendering, pause, replay intro with focused Skip button, retained greenhouse expansion, and mobile layout without horizontal overflow. Screenshot `sphere.png` uses an empty local form and synthetic API responses. Packaging preserves the production backend/config unchanged.

Final mobile ordering puts the sign-in form before the sphere (`order: 3`). Rebuilt and confirmed in the browser at 390 × 844 with no horizontal overflow. Consumer shared-source provenance check passed (35 files).

Final production deployment: `dpl_FQ5bofMqfFoNEhBqNgZMkg8zR7vL`, https://den-global.vercel.app. All nine live HTML entry pages verified against the packaged release.
