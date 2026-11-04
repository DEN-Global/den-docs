# DEN GLOBAL — FULL PLATFORM DEVELOPMENT & MULTI-REPOSITORY EXECUTION PROMPT

## CRITICAL INSTRUCTION: STOP BUILDING ONLY THE WAREHOUSE

You are Codex, acting as the principal software architect, full-stack engineering team, DevOps engineer, database engineer, UI/UX designer, security engineer, and technical project manager for **DEN Global**.

The project owner has confirmed that DEN is a complete global marketplace, transportation, delivery, logistics, warehousing, and international trade platform.

**Your current implementation has concentrated too heavily on the warehouse module. This must change immediately.**

The warehouse module is only one part of DEN Global.

Your new responsibility is to build and integrate the ENTIRE DEN ecosystem, covering all user roles, dashboards, services, APIs, databases, authentication, payments, tracking, communications, and administrative functions.

Do not continue endlessly improving the warehouse while leaving the other applications unimplemented.

## 1. EXISTING WORK — PRESERVE EVERYTHING

The existing private `den-backend` repository reportedly contains:

- Authentication and secure cookie sessions.
- Scrypt password hashing.
- CSRF and origin protection.
- TOTP enrollment and MFA checks.
- Primary Super Admin and Lesser Super Admin policies.
- International Trade locking policies.
- Warehouse business registration and approval.
- Warehouse facility and staff management.
- Employee permissions.
- Warehouse operational records.
- Hash-linked audit records.
- Commission policy logic.
- Approximately 50 locally passing tests, pending confirmation of latest CI.

Do not delete, overwrite, reset, or unnecessarily rebuild these systems.

First inspect the actual repository to verify which features exist.

Reuse working components and extend them through compatible changes.

Do not claim a feature is complete until it is tested.

## 2. GITHUB ORGANIZATION AND REPOSITORY CREATION

GitHub organization: **DEN-Global**

Verify the actual organization slug and permissions before creating repositories.

Create the following private repositories if they do not already exist:

| Repository | Responsibility |
|---|---|
| `den-consumer` | Customer marketplace and shopping experience |
| `den-manager` | Organization management dashboard |
| `den-rider` | Rider registration and delivery dashboard |
| `den-dispatch` | Order dispatch and delivery coordination |
| `den-transport` | Passenger transportation and vehicle services |
| `den-shipment` | Domestic and international shipments |
| `den-warehouse` | Warehouse owners and employees |
| `den-admin` | Primary Super Admin and all sub-admin dashboards |
| `den-backend` | Central Cloudflare Workers API and D1 database |
| `den-payments` | Payment processing and commission management |
| `den-wallet` | Multi-currency wallets and financial ledger |
| `den-chat` | Authorized real-time messaging |
| `den-tracking` | GPS tracking, routes and ETA |
| `den-notifications` | Push alerts and operational notifications |
| `den-shared` | Shared types, contracts, UI components and utilities |
| `den-infrastructure` | Cloudflare configuration and deployments |
| `den-docs` | Documentation, architecture and developer guides |

Create the repositories using authorized GitHub tools or credentials. If repository creation is unavailable, report the precise blocker and continue with implementation work that does not depend on that permission.

All repositories must work together as **one unified DEN platform**.

Use shared API contracts, compatible authentication, coordinated releases, automated tests and documented dependencies.

Do not create disconnected applications that cannot communicate.

## 3. BUILD ALL ROLE DASHBOARDS

Start implementation of the following dashboards immediately.

### A. Consumer Dashboard

Implement:

- Account registration and login.
- Consumer profile and saved delivery addresses.
- Product discovery homepage.
- Search across organizations and products.
- Product categories and filters.
- Organization storefronts.
- Product photos, descriptions, prices and availability.
- Shopping cart and checkout.
- Digital product payment integration interfaces.
- Order history and order details.
- Live rider location tracking map.
- ETA and traffic information where supported.
- Delivery payment on arrival.
- Five-digit delivery verification code.
- Customer QR scanning for final delivery confirmation.
- Combined purchase and delivery receipts.
- Public organization reviews and ratings.
- Community posts and comments.
- Consumer wallet.
- Notifications.
- Customer-to-rider order-specific chat.
- International shipment interface, locked until activation.

Consumers must NEVER have direct private messaging with organizations.

### B. Organization Manager Dashboard

Implement:

- Organization registration and verification workflow.
- Organization profile and storefront.
- Product and inventory management.
- Product image uploads.
- Product pricing and stock updates.
- Sales reports and analytics.
- Incoming orders.
- Order preparation and packaging.
- Ready-for-pickup status.
- Dispatch management.
- Rider assignment monitoring.
- Organization pickup QR code generation.
- Confirm Handoff control.
- Live outgoing-delivery tracking.
- Employee management.
- Custom employee roles and departments.
- Assistant Manager role.
- Sales, inventory, order-processing and dispatch permissions.
- Employee activity and audit logs.
- Internal employee/team chat.
- Manager-to-rider order-specific communication.
- Organization wallet and bank account linkage interfaces.
- Monthly commission statements.
- Subscription plan management.
- Financial reporting and receipts.

Support both solo organizations and organizations with employees.

Do not give sales employees unrestricted dispatch permissions.

### C. Rider Dashboard

Implement:

- Rider registration and verification.
- Full name, profile photo and address.
- Protected identity verification information.
- Vehicle selection and registration.
- Bicycle, motorcycle, car, van, truck and other supported vehicle categories.
- Applicable driving licence and vehicle document requirements.
- Unique Rider ID and identification QR.
- Pending verification dashboard.
- Rider job feed.
- Merchant-affiliated rider priority.
- Independent rider job access.
- First-successful-accept job reservation.
- Decline and reservation release.
- Reserved job status.
- Ready-for-pickup notifications.
- Organization QR scanning.
- Pickup handoff verification.
- GPS location sharing.
- Navigation and route information.
- Delivery arrival workflow.
- Cash or digital delivery payment.
- Cash confirmation code.
- Five-digit delivery verification.
- Rider QR display.
- Earnings and delivery history.
- Rider wallet.
- Rider communities, maximum five memberships.
- Order-specific rider-to-consumer messaging.

Unverified riders may complete onboarding but cannot accept jobs.

### D. Dispatch Dashboard

Implement:

- Incoming delivery requests.
- Organization order status.
- Rider eligibility and assignments.
- Reserved, Ready, Picked Up and Delivered states.
- Dispatch alerts.
- Pickup confirmation.
- Live delivery monitoring.
- Delivery exceptions.
- Emergency employee delivery workflow.
- Assignment history and audit events.

Emergency employee delivery becomes available only under the agreed unclaimed-order fallback concept. The exact timeout and eligibility rules remain configurable and subject to approval.

### E. Transportation Dashboard

Implement:

- Passenger transportation service.
- Driver onboarding.
- Vehicle registration.
- Cars, motorcycles, buses, trucks and supported water transport.
- Passenger pickup and destination selection.
- Route and fare quotation interfaces.
- Ride requests and acceptance.
- Live journey tracking.
- Trip history.
- Driver earnings.
- Independent driver management exception.
- Vehicle-specific eligibility.
- Long-distance transport.
- Transport safety and incident reporting.

Transport prices and service availability must remain configurable by country and vehicle type.

### F. Shipment Dashboard

Implement:

- Domestic shipment booking.
- Shipment pickup and destination.
- Parcel size and weight.
- Vehicle and carrier matching.
- Shipment quotations.
- Shipment tracking.
- Carrier handoff.
- Shipping documentation.
- Delivery confirmation.
- Shipment history.
- International shipping features behind the Primary-only feature lock.

Include architecture for air, sea, road, freight and container shipping.

Do not activate real international trade without authorization and the necessary external integrations.

### G. Warehouse Dashboard

Preserve and extend the existing implementation.

Provide:

- Warehouse owner registration.
- Business verification.
- Multiple warehouse facilities.
- Warehouse staff accounts.
- Receiving, inventory, packing and dispatch permissions.
- Package scanning.
- Storage location tracking.
- Shipment consolidation.
- Warehouse operational reports.
- Warehouse earnings and statements.
- First 30 days commission-free.
- Partner warehouses worldwide.
- Future DEN-owned warehouses.

Warehouse owners manage their own staff. DEN administrators supervise compliance and platform operations.

### H. DEN Admin Dashboard

Implement the complete hierarchy:

**Primary Super Admin**
- Full administrative authority.
- Creates and manages all admin levels.
- Exclusive authority to unlock or relock International Trade.
- Controls global platform settings.

**Lesser Super Admin**
- Full ordinary administrative operational authority.
- Creates and manages ordinary admins.
- Cannot create, modify or remove Super Admins.
- Cannot unlock or relock International Trade.

**Specialized Admins**
- Finance Admin.
- Rider Verification Admin.
- Organization Verification Admin.
- Community Moderation Admin.
- Delivery Operations Admin.
- Shipping Admin.
- Support Admin.
- Security & Audit Admin.
- Global Shipping Admin.
- International Trade Admin.
- Warehouse Admin.

The three international administrative roles remain locked until the Primary Super Admin activates International Trade.

Admin dashboard functionality must include user statistics, organization monitoring, rider approvals, financial monitoring, commission invoices, warehouse approvals, reports, audit logs, operational monitoring and authorized administrative actions.

## 4. CENTRAL BACKEND AND DATABASE

Use Cloudflare as the primary infrastructure.

Build:

- Cloudflare Workers APIs.
- Cloudflare D1 database and migrations.
- Cloudflare R2 object storage.
- Durable Objects where justified for real-time coordination.
- Cloudflare Queues for background events.
- Scheduled Workers for monthly financial calculations.
- Central authentication and session management.
- Server-enforced role-based access.
- Tenant and facility isolation.
- Secure API contracts.
- Webhook processing.
- Audit logs.
- Rate limiting.
- Error handling.
- Monitoring.
- Database backup and recovery procedures.

Use production-minded architecture while remaining compatible with Cloudflare's free tier for the initial application preview wherever practical.

## 5. PAYMENTS, WALLETS AND COMMISSIONS

Build the payment and wallet infrastructure without activating unapproved real-money operations.

All user roles should have appropriate wallet functionality, subject to provider and regulatory support.

Support planned currencies:

- NGN
- USD
- GBP
- EUR

Implement a proper ledger, transaction history, reconciliation and provider integration interfaces.

Product payments are digital.

Delivery payments may be cash or digital on arrival.

Organizations may link supported bank accounts with authorization.

DEN collects commissions monthly rather than deducting commissions from every sale.

Build configurable progressive commission tiers based on:

- Monthly sales.
- Organization type.
- Subscription plan.
- Country.
- Service category.
- Applicable commercial agreements.

All percentages and subscription prices remain provisional pending research and approval.

Warehouse businesses receive their first 30 days commission-free.

Automatic commission collection is optional, administrator-controlled, and permitted only when a valid payment mandate exists. The previously discussed seven-day grace period applies to eligible authorized collections.

Never perform unauthorized bank debits.

## 6. REAL-TIME TRACKING

Build the tracking service shared across consumers, managers, riders, dispatchers, transport providers and shipments.

Include:

- Authenticated GPS updates.
- Moving map markers.
- Estimated arrival times.
- Route calculation.
- Traffic integration where supported.
- Tracking status updates.
- Last-known location.
- Offline/stale-location indicators.
- Location privacy.
- Delivery timeline.
- Pickup and drop-off events.
- Shipment milestones.
- Warehouse scans.
- Tracking history.

Use a real tracking architecture, but allow simulated GPS and provider adapters for local development.

Do not label simulated GPS as live real-world tracking.

## 7. REAL-TIME CHAT

Build `den-chat` as a shared communication service.

Allowed communication:

- Manager to organization employees.
- Manager to internal teams.
- Employee to authorized team members.
- Manager or authorized dispatch employee to assigned rider.
- Rider to assigned consumer for an active delivery.
- Authorized operational communication between warehouse personnel.

Not allowed:

- Direct private consumer-to-organization messaging.
- Unauthorized cross-organization messaging.
- Access to another customer's private delivery conversation.

Implement message permissions, conversation history, delivery status, notifications, abuse reporting and retention controls.

## 8. INTERNATIONAL TRADE — LOCKED

International Trade must remain disabled by default.

Only the Primary Super Admin can unlock or relock it.

Develop the architecture and interfaces for:

- International marketplace trading.
- Global shipping.
- Air freight.
- Sea freight.
- Road freight.
- Containers.
- Freight forwarding.
- Customs documentation.
- Import/export compliance.
- Warehouse networks.
- Carrier integration.
- Customs status tracking.
- Duties and landed-cost estimates.
- International payment interfaces.
- Insurance and claims.
- Restricted-goods screening.
- Global logistics analytics.

All international booking and operational activation endpoints must enforce the lock.

Existing shipments must remain accessible for safe resolution if the module is relocked.

## 9. ADD THE NEW DEN FEATURES

Add these without removing any existing functionality:

1. DEN OneTrack — unified package and shipment tracking.
2. DEN Smart Match — intelligent rider, vehicle and carrier matching.
3. DEN Pricing Lab / Price Guard — commission and profitability simulations.
4. DEN Trust Passport — reusable verified partner status.
5. DEN Shield / Safe Handoff — fraud detection and verified transfers.
6. DEN Trade Pilot — controlled country-by-country expansion.
7. DEN Route Brain — route optimization.
8. DEN Partner Scorecards — service quality monitoring.
9. DEN Business Hub — merchant integrations and APIs.
10. DEN Rescue Flow — delivery exception and recovery management.
11. DEN Offline Ops — resilient offline-capable operational workflows.
12. DEN Expansion Control — staged regional and international feature activation.

These are additive features. Implement them progressively and document their readiness.

## 10. IMPLEMENTATION PRIORITIES — DO NOT STAY ON ONE MODULE

The project must now progress across multiple applications.

**Phase 1: Platform Foundation**
- Inspect existing work.
- Create missing repositories.
- Establish shared API contracts.
- Establish authentication and authorization.
- Set up database and infrastructure.

**Phase 2: Core User Applications**
- Consumer dashboard.
- Manager dashboard.
- Rider dashboard.
- Admin dashboard.
- Working navigation and authenticated data.

**Phase 3: Marketplace**
- Product management.
- Product search.
- Cart.
- Checkout.
- Orders.
- Inventory.
- Receipts.

**Phase 4: Delivery**
- Rider registration.
- Job alerts.
- Rider reservations.
- Dispatch.
- Ready status.
- QR pickup.
- Confirm Handoff.
- Live tracking.
- Delivery verification.

**Phase 5: Communications and Finance**
- Real-time chat.
- Notifications.
- Wallet ledger.
- Payment provider sandbox.
- Monthly commission engine.

**Phase 6: Transportation and Warehousing**
- Passenger transport.
- Vehicle-specific services.
- Warehouse partner operations.
- Facility and staff management.
- Domestic shipment management.

**Phase 7: International Trade**
- Develop all locked international interfaces.
- Carrier and customs integration adapters.
- Country-specific configurations.
- Global warehouse network.
- International trade administration.

**Phase 8: Advanced DEN Features**
- Intelligent matching.
- Route optimization.
- Fraud detection.
- Partner scoring.
- Developer APIs.
- Business intelligence.
- Offline operations.

**Phase 9: Integration, QA and Cloudflare Preview**
- Connect all applications.
- Run integration tests.
- Validate permissions.
- Run end-to-end scenarios.
- Deploy a preview when authorized and configured.
- Monitor free-tier usage and external provider costs.

Do not wait until every warehouse enhancement is finished before starting the consumer, manager, rider and admin applications.

Work on independent modules in parallel where the development environment permits, while keeping shared API contracts stable.

## 11. STRICT ENGINEERING REQUIREMENTS

- Never delete existing project work.
- Never reset repositories or databases without explicit authorization.
- Never hardcode credentials.
- Never expose sensitive verification documents.
- Never claim a payment integration is live when it is only mocked.
- Never invent a final commission percentage.
- Never activate the refund policy; it remains deferred.
- Never bypass the Primary Super Admin international-trade lock.
- Never allow unauthorized role combinations.
- Never allow multiple riders to reserve the same job simultaneously.
- Never allow package pickup before Ready and Confirm Handoff.
- Never mark a delivery completed without the required verification.
- Never create disconnected dashboards that cannot communicate through the backend.
- Use migrations, versioned contracts and automated tests.
- Maintain documentation in every repository.
- Ensure the application remains mobile-friendly.
- Provide clear error messages and loading states.
- Maintain auditability for sensitive operations.

## 12. REQUIRED CODEX OUTPUT AND ACTIONS

Start immediately with these actions:

1. Inspect `DEN-Global/den-backend` and verify its actual implementation.
2. Inspect the GitHub organization for existing repositories.
3. Create all missing repositories when authorized.
4. Establish shared architecture and integration contracts.
5. Create an implementation tracking document showing every repository, its status and dependencies.
6. Build working application shells for Consumer, Manager, Rider and Admin first.
7. Connect those shells to the existing authenticated backend.
8. Implement the first complete marketplace-to-delivery workflow.
9. Continue implementing the remaining modules in prioritized milestones.
10. Run tests and builds after each milestone.
11. Commit and push completed work to the correct repositories when authorized.
12. Report what is complete, partially complete, mocked, blocked and not started.

**Do not respond only with another plan or architecture document.**

After a brief repository assessment, begin making real code changes.

If blocked by missing permissions, credentials or unavailable tools, identify the exact blocker and continue other independent implementation work.

Do not claim the entire platform is complete after creating empty repositories or placeholder dashboards.

## FINAL DIRECTIVE

DEN Global is ONE unified platform, not a warehouse-only application.

The immediate priority is to expand development into the Consumer, Manager, Rider, Dispatch and Admin applications while preserving and reusing the warehouse backend.

Build real working software, connect it through secure APIs, test it and maintain compatibility across repositories.

The project owner will handle decisions requiring explicit business approval.

**Begin the multi-repository implementation now.**