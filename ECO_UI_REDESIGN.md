# Compact DEN Global UI redesign — 4 November 2026

User-approved interpretation: apply the GreenFuture and EcoNexa visual language to DEN Global. User review then requested a compact layout. The implementation keeps DEN's workflows and uses local organization/order data.

## Verified result

Consumer has a compact split hero, generated commerce illustration, organization-first discovery cards, focused store-search action, connected My orders action and preserved cart/catalog/review behavior. Manager has a compact storefront hero, organization profile/selector, registration/edit drawers, real inventory counts and product form/table. The common theme updates account, community, tracking, wallet, notifications and security surfaces without changing their APIs. The other role applications receive the matching palette/control system.

All 8 applications build. Shared API tests (3), infrastructure configuration tests (5), five vendor snapshot checks (23 files each), Transport/Shipment syntax checks, the infrastructure static checks and whitespace checks pass. The stale portal checker was updated to validate the existing common sign-in/private workspace policy rather than require the removed public role directory. No backend behavior changed in this visual pass; the preceding 93-test backend result is not presented as a fresh run.

In-app browser verification: Consumer/Manager page identity and nonblank rendering; no framework overlay; no warnings/errors in the final Consumer run; Explore organizations focuses organization-search; real organization search filters the database-backed cards; My orders opens order history; Manager registration and Add product drawers open/close with their required fields. A narrow viewport measured 479×844 with document scrollWidth equal to clientWidth; the explicit 390 setting instead measured 831px, so an exact 390px claim is not made. Desktop measured 1614×1347. Temporary overrides were reset.

## Visual comparison ledger

Reference images: `../design/eco-redesign/consumer-concept.png` and `manager-concept.png` from the workspace root design directory. Production asset: `den-shared/src/commerce-island.png`. References and browser screenshots were inspected with view_image; DOM computed styles were also checked.

| Comparison | Evidence / result |
|---|---|
| Copy | Consumer and Manager hero headlines/actions retain the generated DEN direction. Organization names and descriptions bind actual local records. Above-fold copy differences are intentional: cart remains available, workspace/account identity and trade status remain, original order-table columns remain. |
| Layout/density | Sidebar, split hero, organization cards and table structure match the direction; smaller hero/sidebar/spacing intentionally follow the user's compact correction. |
| Typography | Inter controls and Space Grotesk headings verified through computed styles (Manager heading 44px/600, brand 22px/700, primary buttons 13px/600 at desktop). |
| Palette | White navigation/cards, #F4F4F4 workspace and #5C7D52 primary actions/highlights; original lime/dark sidebar replaced. |
| Card treatment | Rounded cards, monogram/logo, about copy, restrained shadow, green lower edge and arrow links; real longer organization names wrap safely. |
| Asset treatment | Separate generated shop/van scene replaces energy video. Shared illustration deliberately used for Consumer/Manager; matching backdrop prevents a visible image rectangle. |
| Responsive/motion | Narrow cards stack; header/actions remain accessible; bottom navigation scrolls; no page overflow at measured479px; reduced-motion rules disable decorative animation. |

Screenshots captured through the in-app browser: `/tmp/den-eco-final-review.png`, `/tmp/den-eco-manager-native.png`, `/tmp/den-eco-phone.png`. Browser screenshot scaling/cropping did not reliably match the 1536×1024 concept size; final comparison used actual desktop/narrow layouts and documented density changes, rather than claiming a pixel-perfect clone.

The implementation was visually checked against the design direction and the compact user correction. Existing workflows were preserved; no material layout blocker was found on the checked Consumer/Manager surfaces. Authenticated Rider/Dispatch/Admin/Warehouse/Transport/Shipment flows were built but not individually exercised in this design pass. Real email delivery, live payments and carrier integrations retain their previously documented configuration limits. No Cloudflare deployment was performed.
