# Foreground delivery GPS

Riders: open Delivery jobs → View order → OneTrack → Start sharing GPS. Permit device location. The assigned customer can use Delivery map and choose Load delivery map. Location is shared only for an active assigned delivery; the server also requires an approved rider.

The sharing session belongs to the signed-in rider workspace, so it survives closing the order drawer and changing workspace pages. A visible status bar provides Stop sharing. Sign-out, closing/reloading DEN or ending the assignment stops sharing; the server rejects writes after release/reassignment/delivery. Hidden tabs and offline connections pause collection and drop pending positions; resuming requires a fresh GPS fix and assignment validation. No automatic restart after reload, offline queue, background/locked-screen tracking, traffic or ETA is promised.

Posts are throttled to 15 seconds with the newest valid GPS fix. Assigned customers poll at 15 seconds. No fix is invented when the phone has not provided one. Old locations remain labeled stale after two minutes; simulated positions retain their label. MapLibre + OpenFreeMap loads only after the viewer chooses it. The rider marker updates in place; a follow control recenters after panning. The reported accuracy area is drawn locally and map attribution stays visible. Both light and dark styles are available.

Validation: 15 shared tests and 7 backend service tests pass. Includes actual device payload format, throttling, cleanup, late callbacks, paused/offline handling, invalid fixes, existing timestamps, no concurrent writes, permission denial, participant isolation, suspended riders and ended assignments. Isolated browser review verifies the consent copy and start control. No real device coordinates were collected by the agent; actual two-phone GPS delivery remains to be tested by the owner. Production API/configuration remain unchanged in the UI release.

## MapLibre integration

MapLibre GL JS 6.18.0 is pinned and lazy-loaded, with a same-origin worker. OpenFreeMap liberty/dark styles supply tiles, glyphs and sprites. No map key or billing account is configured. The deployment CSP allows only https://tiles.openfreemap.org for map requests/images and self for workers; Google iframe access was removed. API code and other production configuration are preserved.

Validation: 17 shared tests pass, including map coordinate bounds and spherical accuracy geometry; all nine workspace builds pass. Browser review with explicitly simulated GPS verifies tiles, marker, accuracy, attribution, keyboard pan, follow/recenter, light/dark themes and narrow layout under the intended CSP. Supplier styles emitted warnings for a few missing optional POI icons, but streets and rider markers loaded. Real-device GPS remains a separate owner test. Routing, traffic, geocoding and ETA are not added by the map renderer.
