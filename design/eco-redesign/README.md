# DEN Global — GreenFuture × EcoNexa adaptation

The user confirmed that the two supplied energy-site specifications are visual references for DEN Global, not a separate energy website. During live review the user requested a more compact layout. That density correction takes precedence over the initial concepts.

## Design references and asset

Built-in Image Gen produced `consumer-concept.png`, `manager-concept.png`, and the standalone production illustration at [den-shared production artwork](https://github.com/DEN-Global/den-shared/blob/codex/unified-account-entry/src/commerce-island.png) (also synchronized into the five role-app vendor snapshots). The production UI is real React/HTML/CSS; the images are not used as interactive screenshots.

Consumer concept prompt: premium 1536×1024 DEN Global local shopping/delivery dashboard; white 230px navigation with Discover, My orders, Delivery map, Community, Profile, Wallet, Notifications, Security; #F4F4F4 canvas, sage #5C7D52 controls, Inter body, Space Grotesk headings; split hero “Your community. / Closer than ever.” and “Discover organizations, explore their stores, and follow every delivery.”; Explore organizations and My orders actions; separate 3D neighborhood shop/van/island visual; real organization cards with monograms/logos, about text and Visit store; real order table. No fabricated claims, metrics, ratings or brands.

Manager concept prompt: same visual family, Organization/Incoming orders navigation, modest hero “Your storefront. / Ready for what’s next.”, Register organization action, organization selector and active status, Edit storefront, Product catalog/Add product, three actual inventory counts, and real catalog table. No fake revenue or analytics.

Production asset prompt: standalone premium 3D miniature isometric island for DEN Global; cream neighborhood shop, green-and-white awning, produce crates, trees/shrubs, white delivery van with four-square green mark, two kraft parcels, oval grass island/earth edge and curved road; soft studio lighting, clay/paper textures, #5C7D52/#009E52 accents, horizontal 3:2 composition; no UI, wording, turbines, solar panels or stock photography. Generated as a separate asset, stored locally, blended into the hero with a matching backdrop.

## Implementation decisions

- Keep React/Vite and the existing native CSS/components; the two pasted prompts prescribe incompatible Tailwind versions, so a dependency migration would not improve the requested visual result. Motion uses small CSS transitions/entrance animations with reduced-motion support.
- Green-energy brand copy, videos, energy projects and fabricated trusted-by brands are replaced by DEN commerce content and the generated DEN illustration.
- Compact follow-up: 212px sidebar, 62px topbar, 260px Consumer hero, shorter Manager hero, tighter cards/metrics and reduced vertical spacing. Narrow layouts stack cards and use a scrollable bottom navigation.
- Shared role components retain their server-backed behavior. Public signup, private Admin routing, role restrictions and database policies were not changed for this redesign.
- Shared palette/components cover Consumer, Manager, Rider, Dispatch and Admin. Warehouse receives the same theme. Transport/Shipment retain their simpler native forms with matching colors, surfaces and control styling; those two retain system-font fallbacks.
