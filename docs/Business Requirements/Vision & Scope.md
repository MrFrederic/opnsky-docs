# Vision & Scope

## Business Requirements

### Background

“DOSAAF Aeroclub Minsk” (referred to as “the Dropzone”) is a premier skydiving center in Minsk, Belarus. The Dropzone offers:

- Tandem jumps
- Individual static line jumps with paratrooper parachutes
- Sport jumps for licensed skydivers (“paid skydivers”)
- Training programs (AFF, static line with canopy, classic programs)
- Skydiving events and equipment rental

Additionally, the Dropzone operates a government-sponsored school for training sport skydivers in various disciplines for national and international competitions.

#### Current tandem booking process (as-is)

The Dropzone manages tandem bookings using a partially rewritten open-source booking tool (EasyAppointments), manual notes, and Telegram groups/chats.

Process outline:

1. Customers submit an online form and are added to a day-specific Telegram group where they must confirm their booking.
2. The group is used to share pre-jump information (time, place), answer questions, and post weather updates.
3. After confirmations:
   - The administrator checks instructor availability.
   - Adds deferred tandem jumpers (e.g., weather delays).
   - Posts remaining slots in a public Telegram channel and fills them on a first-come-first-served basis.

Pain points:

- Fragmented systems and manual reconciliation
- High admin effort to confirm, reschedule, and communicate
- Limited visibility into real-time capacity

#### Current jump tracking process (as-is)

Jumps are recorded in a paper logbook for legal compliance. A sport skydiver fills the log on the line-up/manifest just before each load, capturing:

- Jumper name
- Jump type
- Number of jumps (experience)
- Canopy type and serial/ID (for rentals)

After each jump week, management aggregates paper data for legal and statistical reports.

Pain points:

- Manual, error-prone data entry
- Delayed and costly reporting
- Limited auditability/search
- Difficult equipment usage tracking

### Business Problems & Opportunities

Problems:

1. Inconsistent website experience and unclear user journeys (tandem vs training vs sport), leading to customer confusion and high admin support load.
2. Limited online booking capabilities; no streamlined, capacity-aware scheduling → lost sales and increased manual work.
3. Inefficient customer management and day-of-operations coordination via ad hoc Telegram groups.
4. Outdated jump tracking → slow reporting, low data quality, and compliance risk.

Opportunities:

- Centralize booking, communications, and operations through a Telegram mini app, bot and semi-automatically managed Telegram chats.
- Digitize jump manifest/logbook to improve data quality, enable instant reporting, and reduce legal/compliance risk.
- Improve conversion and customer satisfaction with a guided booking flow and automated reminders.

### Business Objectives (SMART) - To Be Refined

Business objectives are limited due to lack of baseline data.

By June 1, 2026 (1-2 month after season start), achieve:

- Conversion & sales:
  - >85% booking completion rate after starting the flow.
- Operational efficiency:
  - -50% admin time spent per jump day on booking coordination (subjective, post-implementation survey).
- Compliance & data quality:
  - 100% of jumps recorded in a digital logbook with 99.5% record completeness.
  - Weekly legal and statistical reports generated in <5 minutes (previously hours).
- Customer satisfaction:
  - Post-jump CSAT ≥ 4.5/5 for tandem customers.
- Reliability:
  - <1% unplanned downtime on weekends during the season.

### Success Criteria

- MVP released and used for at least 4 consecutive jump weekends before May 31, 2026.
- At least 80% of tandem bookings originate and are managed end-to-end in OPNsky.
- All loads/manifests submitted digitally and exportable to required formats.
- Photo/video delivery available within 24 hours for ≥90% of tandems.
- Positive feedback from admin, instructors and manifest managers (≥4/5 usability survey).

### Vision Statement

For tandem customers, OPNsky is a Telegram mini app and bot that provides an intuitive way to book tandem jumps, receive timely updates and access photos/videos—delivering a seamless, confident experience from website to jump day.

For Dropzone administrators/manifest, OPNsky is an operations console that streamlines capacity planning, booking management and customer communications.

For instructors and camera flyers, OPNsky is an easy way to share captured media with customers and keep track of their jump logs.

For Dropzone management, OPNsky is an operational data platform that improves efficiency and decision-making.

### Business Risks

- Adoption risk: customers or staff prefer current Telegram-only flow/manual processes.
- Platform dependency: reliance on Telegram mini app and Bot API stability or policy changes.
- Regulatory/compliance: data residency, personal data protection, audit trail requirements.
- Weather/operational variability: frequent reschedules stress the booking model.
- Change management: training instructors/admin; season timing constraints.

### Assumptions & Dependencies

- Telegram mini apps and Bot API remain available and allowed in the operating region.
- Instructor schedules can be represented as resources with time slots.
- Hosting with acceptable data residency and uptime can be provisioned.

## Project Scope

### In-Scope (overall product)

- Customer-facing Telegram mini app and bot:
  - Guided tandem booking (date, language, weight constraints, options)
  - Reminders, confirmations, rescheduling/cancellation
  - Post-jump media access and reviews/CSAT
- Admin/manifest console (web):
  - Capacity/resource planning
  - Load building and manifesting; on-site check-in (prioritizing fast, right-before-jump workflows)
  - Digital logbook with audit trail
  - Equipment usage tracking
  - Reports (legal, financial, utilization, safety)
  - Role-based access control and activity logs
  - Usage analytics dashboard (Google Analytics or similar)
- Integrations:
  - Telegram Bot API
  - Telegram Mini App
- Content/website:
  - Clear user journeys (tandem, student, sport)

### Out-of-Scope

- Inventory and rental management
- Training program workflows (AFF, static line courses)
- Sport skydiver bookings and manifests
- Online payments
- E-signature waivers

### Major Features

- Booking engine with capacity management
- Cancellation and rescheduling workflows
- Operations: check-in, load manifesting, instructor/camera assignment
- Digital logbook entries with exports for regulators
- Media ingestion, linking to bookings, delivery to customers
- Notifications and reminders (Telegram-first; optional email/SMS)
- Automatic day-of-operations Telegram group management

### Scope of MVP (target: March 2026)

- Tandem booking for single jumpers of groups; simple reschedule/cancel
- Basic notifications (reminders, status updates) via bot
- Jump confirmations via bot
- Automatic day-of-operations group management
- Admin console: capacity setup, system settings
- Booking management: day view, quick editing, cancellations
- Load check-in
- Minimal digital logbook: list of jumps with minimal details
- Reports: weekly jump summary
- Basic roles: 
  - Admin, Instructor (for filtering and media upload)
  - Photographer (for filtering and media upload)
  - Sport Skydiver (view own jumps)
  - Customer (book, view own bookings)
- Audit logs for critical actions
- Default usage analytics dashboard

### Scope of Subsequent Releases

- Media: manual upload per booking, delivery link to customer
- Student/training programs (AFF/static line) workflows
- Equipment lifecycle, inspections, and incident reporting
- Vouchers/gift cards
- Offline-friendly manifesting
- Advanced analytics;

### Limitations and Exclusions

- Offline mode limited to local browser caching; no guaranteed full offline operations.
- E-sign waivers and payments excluded; handled on-premise.
- Photo/video editing and watermarking outside system scope (ingest + deliver only).
- No guaranteed multilingual support beyond in MVP.

## Business Context

### Stakeholders - To Be Refined

- Dropzone Management
- Chief Instructor / Safety Officer
- Booking Administrator
- Manifest/Check-in Staff
- Tandem Instructors
- Camera Flyers/Photographers
- Sport Skydivers and Students
- IT/Operations (hosting, backups, access control)

### Project Priorities

- Must-have by season start: reliable booking, manifest, digital logbook, basic reports.
- Schedule is fixed (season start in spring 2026); scope negotiable; quality must support weekend peaks.

### Deployment Considerations

- Hosting (pending decision) either:
  - Self-hosted on private infrastructure of one of the sportsman (possible downtime, unreliable data storage, requires maintenance).
  - Cloud-hosted (preferred) with data residency in Belarus.
- Security: Telegram authentication, RBAC, encrypted data in transit, audit logs, least-privilege.
- Data privacy: data retention policies, right-to-erasure process.
- Performance: support peak loads (e.g., up to 100 concurrent users).
- Observability: monitoring, alerting, error tracking; rollback plan and staged releases.
- Business continuity: exportable data (open formats).
