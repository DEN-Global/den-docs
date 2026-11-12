# DEN Network UI verification — 2026-11-11

## Scope
Nine frontend workspaces: Consumer, Manager, Rider, Dispatch, Admin, Warehouse, Transport, Shipment, Pets. Styling is shared through den-shared/src/network-theme.css, network-mobility.css, and a pet-directory adapter. The 3D scene uses locally bundled Three.js 0.170.0. No authentication migration, database mutation or provider configuration is part of this release.

## Reference and adaptations
The supplied Medusa JF-4 reference contributes pale mint grounds, deep green ink, thin borders, compact labels, timeline controls and procedural geometry. User selected DEN delivery network and parcels in place of the jellyfish. Pinterest logistics search was reviewed in the browser, including Shipment Logistic Dashboard and Carvex Logistics Webapp 2024. Preserve all original product copy and limits; illustration captions explicitly identify the scene as illustrative, not live tracking.

## Validation
- All nine production frontend builds passed.
- Shared API and contract tests: 3 passed.
- Consumer, manager, rider, dispatch and admin vendor provenance checks passed (30 source/contract files).
- Mechanical UI detector returned no findings for the core new CSS and scene components.
- IAB desktop inspection covered sign-in, consumer marketplace, manager catalog/form drawer, rider application, dispatch table, admin overview, warehouse overview, transport quotation, shipment inputs and pets directory/profile form.
- Mobile viewport requested at 390x844. The in-app browser reports a CSS viewport of 355px due to its display scaling; the document width was 345px, with no horizontal content overflow. Inspected marketplace bottom navigation, pet-profile form and sign-in. On mobile, sign-in precedes the illustration.
- Tested scene pause, parcel focus, playhead update; registration switch correctly preserves the disabled email verification state; storefront and product-detail navigation; manager form drawer; pet profile navigation and modal; light/dark theme switching.
- Runtime fixture issue in local storefront comments was corrected in the isolated test server. Synthetic data and the test server are excluded from deployment.
- Warehouse asset base is now /warehouse/, avoiding dependence on shared root asset paths.
- Companion starts collapsed and shares the mint/green theme, so it does not obscure form controls.
- Release packaging verifies every entry-point asset exists and preserves all 28 production API/vendor/package/configuration files byte-for-byte.

## Limits
Live sign-in and email delivery are not validated with an account: email verification remains unconfigured. Protected workflows were visually inspected with isolated synthetic local data. Existing backend permissions and all live financial restrictions remain in force. Three.js is lazy loaded and uses a capped pixel ratio; reduced-motion preference starts the illustration paused. No image-generated or copied Pinterest artwork is included.

## Production result
Deployment dpl_ER7x3oucxnikj2dpyMqkfNyVE2Mq is READY and aliased to https://den-global.vercel.app. All nine workspace HTML routes and their entry JS/CSS returned 200. API health returned 200, auth options returned email verification disabled, and anonymous /api/auth/me returned 401. Live IAB verified the procedural model renders and recorded no console errors. A clean screenshot of the identical locally built sign-in screen is saved in network-ui/network-preview.png with empty fields. The deployed screen was separately verified in IAB.
