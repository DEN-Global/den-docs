# DEN complete UI/UX screen inventory

Design coverage is separate from implementation readiness. Future provider-backed features remain labelled planned or sandbox. Each batch must be verified in Stitch before being marked generated; a submitted prompt is not proof of completion.

| Batch | Screens / flows | Status |
|---|---|---|
| 01 Role foundations | Consumer discovery; Manager products; Rider jobs; Dispatch operations; Transport hub; Shipment hub; Warehouse facilities; Admin control center | Generation requested |
| 02 Identity and account | Welcome/workspace selection; sign-up; sign-in; email verification; password recovery; MFA setup/challenge/recovery; profile; addresses; notification preferences; role conflict and verification pending | Specified |
| 03 Consumer commerce | Search/categories/filter; storefront; product detail; cart; checkout/address/payment choice; digital product payment result; order history/detail; arrival payment; five-code + QR completion; combined receipt; review/community | Specified |
| 04 Manager organization | Business application/documents; storefront editor; product editor/media; stock adjustment; order preparation; pickup QR + Confirm Handoff; staff invitation; custom roles/departments/Assistant Manager; sales/reporting; subscription/bank interfaces | Specified |
| 05 Rider operations | Identity/vehicle/doc onboarding; Rider ID/QR; pending/rejected; eligibility/job feed; reserve race/won/lost; reserved/release; Ready notification; organization QR scan; pickup gate; navigation/arrival; cash/code/QR verification; earnings/history; five communities | Specified |
| 06 Coordination and communications | Dispatch queue/map; assignment detail/history; exception/Rescue Flow; emergency fallback unavailable/configurable; consumer-rider chat; manager-rider chat; internal team chat; tracking timeline/map/stale/offline; notifications | Specified |
| 07 Finance | Consumer/organization/rider wallet; ledger/transaction detail; pending/unavailable withdrawal; combined receipts; monthly commission statement; approved/unapproved Pricing Lab; subscriptions; bank authorization; seven-day mandate collection controls/dispute hold | Specified |
| 08 Transport and shipments | Passenger pickup/destination; route/fare unavailable and quote; request/accept/trip; safety incident; driver/vehicle eligibility; domestic parcel booking/size/weight; quote/carrier match; tracking; handoff/documents/history; long-distance and air/sea/container planned interfaces | Specified |
| 09 Warehouse | Business/facility onboarding; staff permissions; receiving scan/condition; storage location; inventory movement; packing/consolidation; dispatch/carrier handoff; operational report/earnings/30-day holiday; DEN-owned future variant | Specified |
| 10 Administration | Primary/Lesser/ordinary role views; admin creation/permissions; organization/rider reviews/private documents; warehouse compliance; finance/invoices/mandates; community moderation; delivery/shipping/support/security queues; audit detail; country settings; fresh-MFA trade unlock/relock | Specified |
| 11 International and advanced | Locked trade landing; safe historical shipment resolution; country activation/Trade Pilot/Expansion Control; customs/documents/restricted goods/landed cost/insurance planned; OneTrack; Smart Match; Trust Passport; Shield; Route Brain; Scorecards; Business Hub; Rescue Flow; Offline Ops | Specified |
| 12 Mobile | Consumer browse/product/cart/checkout/order/tracking/chat/verification; Rider onboarding/job/reservation/scan/arrival/cash/code/QR; mobile manager/dispatch/warehouse/admin navigation and forms | Specified |
| 13 System and accessibility | Reusable components; skeleton/empty/error/success; permission denied; stale/offline/conflict; upload failed; code expired/retry/rate limit; suspended account; no provider; locked modules; keyboard/focus/reduced motion | Specified |

## Common parts to design

Brand and navigation; workspace/account selector; search; categories/filters; tables and mobile records; maps with honest location/ETA state; timelines; inputs/validation; upload/private document access; product imagery; drawers/dialogs; confirmations; notices; QR scanner/display/manual fallback; OTP/fresh MFA; money/currency/ledger; permission matrix; approval workflow; charts with labelled sample data; receipt/export; audit log; pagination; offline queue conflict resolution; responsive touch targets and accessible focus.

## Critical UX invariants

No consumer–organization private messaging. No ordinary manager+rider combination. No unverified job acceptance. One server-confirmed rider reservation. No pickup before Ready, organization QR scan and Confirm Handoff. No completion without five-digit code and customer scan of rider QR. Cash confirmation code separate. No cash credited twice. Five rider communities maximum. No automatic unapproved rates, refunds, debits or international activation. Only Primary can change the global trade lock after fresh MFA. Existing shipment history remains readable when relocked.
