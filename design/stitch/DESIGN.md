# Design System: DEN Global

## Visual theme and atmosphere
One Network. Every Journey. A coherent global marketplace, mobility and logistics product. Calm, trustworthy, practical and premium. Balanced density for everyday workspaces; compact tables only for professional operations. Eight connected role workspaces share identity and components. A workspace selector never grants privileges.

## Color palette and roles
- Forest (#102B26): navigation, headings and brand foundation.
- Lime (#D7F466): the single action accent; primary actions, current navigation and controlled emphasis.
- White (#FFFFFF): page and surface canvas.
- Ink (#18332B): primary content text.
- Muted (#62696C): supporting copy; maintain WCAG AA contrast.
- Border (#D8DDDC): restrained structure and dividers.
- Pale lime (#F1F8DE): informational/approval surfaces. Errors and warnings use labelled semantic colors and icons, never color alone.
No neon, purple/blue gradients, pure black, glass panels or decorative dashboard chrome. No separate color identity for each role.

## Typography
Manrope for brand, headings and interface text, preserving the existing DEN identity. JetBrains Mono for references, tracking numbers and dense numeric comparisons. Sans-serif throughout software screens. Desktop h1 32–44px, h2 24–28px; mobile h1 28–32px. Body 16px with 1.5–1.65 leading, metadata no smaller than 12–14px. Readable text lines no wider than 65 characters. Use tabular numeric alignment for money and quantities.

## Layout and navigation
Desktop: forest left navigation, clear role label and account/workspace switcher, white task canvas. Information hierarchy follows user tasks, not repetitive metric cards. Tables for operational queues; editorial product imagery and useful categories for consumer discovery. Maps occupy useful space only in tracking/dispatch/trip screens. One primary action per task area. No giant marketing heroes inside operational forms.
Mobile: bottom navigation for consumer/rider core tasks; drawer navigation for professional roles. Single-column content under 768px, no page overflow, tables become labelled record lists. 44px minimum touch targets, visible focus, safe-area spacing and keyboard-aware forms. Build actual mobile variants rather than shrinking desktop.

## Components and states
Shared buttons (primary, secondary, quiet, danger, disabled, busy), labelled inputs, password/OTP, selects, search/filter chips, quantity controls, date/currency selectors, file upload and private-document indicators, drawers, dialogs, accessible toast/status, skeletons, empty states, inline errors, offline/stale indicators, audit timeline, tables/list rows, avatars, QR scanner/display, receipt, map controls, permission selectors and step progress.
Cards only when a distinct object or elevation matters. Prefer open spacing and dividers to equal three-card grids. Keep forms editable and actions explicit. Explain why a disabled action is unavailable and how to resolve it. Sensitive operations need confirmation and fresh authentication UI. Show realistic synthetic data labelled “Design sample”; no invented live metrics, approved fees or performance claims.

## Interaction and motion
150–220ms purposeful transform/opacity transitions; gentle spring feedback (stiffness 100, damping 20). Small status pulse only while an active background update is in progress. Stop loops on completion; honor reduced motion. Loading skeletons mirror content geometry. No animated layout dimensions, floating text or decorative perpetual movement.

## Business and safety constraints
- Consumer private messaging with organizations is prohibited. Public reviews/community comments are separate from authorized rider chat.
- Ordinary store manager and rider modes cannot combine; independent transport driver has its documented exception.
- Products are digitally paid; delivery payment is cash or digital on arrival. Display separate payments and one combined receipt. Cash is never also a withdrawable digital credit.
- Rider reservation is server-confirmed, first successful accept wins. Unverified riders cannot accept jobs. Merchant priority and fallback are configurable, not invented.
- Pickup requires Ready, assigned rider scanning organization QR, and employee Confirm Handoff. Delivery requires the five-digit code followed by customer scan of a short-lived rider QR; separate cash confirmation code.
- At most five rider community memberships.
- Warehouse business commission holiday is first 30 elapsed days after verified business approval, not staff/facility registration.
- Primary alone unlocks/relocks International Trade with fresh MFA. Lesser cannot manage any Super Admin. Three international admin roles remain locked until activation. Historical shipments stay visible for safe resolution after relocking.
- Rates, subscriptions, delivery fares and commission percentages remain provisional. Pricing Lab shows unapproved simulations; collections require mandate/notice/holds safeguards. Refund policy is deferred, not activated.
- Live provider, GPS, payment, identity and compliance capabilities must be labelled accurately. Design future capabilities without asserting current implementation or live activation.

## Anti-patterns
No fake revenue or partner counts, fabricated testimonials, generic names, emoji decoration, broken image links, overlapping content, arbitrary per-role branding, equal card grids replacing useful tables, ambiguous destructive actions, inaccessible low-contrast text, unsupported map ETAs, or “verified” badges without actual verification state.
