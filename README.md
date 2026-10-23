# Technical Specifications Document

## 1. Title Page

- **Project Name:** EventSphere — Event Booking and VIP Experience System
- **Version:** 1.0
- **Date:** October 23, 2026
- **Author(s):** Joseph (Team Leader), Loisa, Gianna, Paolo

---

## 2. Table of Contents

1. [Title Page](#1-title-page)
2. [Table of Contents](#2-table-of-contents)
3. [Introduction](#3-introduction)
4. [Overall Description](#4-overall-description)
5. [Visual Mockup Reference](#5-visual-mockup-reference)
6. [Features](#6-features)
7. [Functional Requirements](#7-functional-requirements)
8. [Non-Functional Requirements](#8-non-functional-requirements)
9. [Data Requirements](#9-data-requirements)
10. [External Interface Requirements](#10-external-interface-requirements)
11. [Glossary](#11-glossary)
12. [Appendices](#12-appendices)

---

## 3. Introduction

### Purpose
EventSphere is a web-based event booking system that helps customers discover concerts and special events, book tickets, and explore exclusive VIP experiences such as Meet & Greet packages. It also gives Producers tools to manage their own events and gives Admins control over the overall platform.

The client wants the platform to stand out from existing ticketing sites (Live Nation, Ticketmaster, StubHub) by rethinking how VIP packages are presented, so that customers perceive more value in them and have a better booking experience.

### Problem Statement
Customers need a convenient way to discover upcoming shows, review event details, and book tickets. Event organizers need a system to manage events, ticket availability, and exclusive VIP packages. EventSphere brings these together in one platform.

### Objectives
- Provide an engaging interface for discovering upcoming and featured events.
- Allow customers to book tickets **without creating an account beforehand**.
- Support **optional** account creation after a successful purchase.
- Offer standard tickets and configurable VIP packages, with a dedicated VIP experience page.
- Allow Producers to manage their own events.
- Allow Admins to manage the overall platform.
- Generate printable PDF tickets with unique QR codes after payment confirmation.
- Validate tickets securely at event check-in and prevent duplicate entry.

### Scope

**In scope**
- Homepage with upcoming and featured events
- Event listing, search, filtering, and event calendar
- Event details page (one page per event)
- Guest checkout and optional post-purchase account creation
- Customer profile (personal information, booking history)
- Dedicated VIP Guide page, Meet & Greet packages, and Special Access packages
- Producer event management and Admin platform management
- Payment confirmation, PDF ticket generation with unique QR codes
- Ticket validation at check-in

**Out of scope (current version)**
- Email delivery of tickets
- Native mobile apps (the web app is responsive for mobile and tablet)
- Resale / secondary ticket marketplace
- Refund automation (handled manually by Admin)

### Definitions, Acronyms, and Abbreviations

| Term | Meaning |
|------|---------|
| TSD | Technical Specifications Document |
| VIP | Very Important Person (premium package tier) |
| ERD | Entity-Relationship Diagram |
| QR | Quick Response (code) |
| API | Application Programming Interface |
| CRUD | Create, Read, Update, Delete |
| JWT | JSON Web Token |

### References
- Zuitt MCP Side Project 1 — Task Specification and client reference slides (#1 to #8)
- Reference applications: Live Nation, Ticketmaster (homepage, event listing, calendar, featured events, event details, customer profile, VIP Guide, Meet & Greet, Special Access VIP packages)
- Sample ERD provided in the task specification

---

## 4. Overall Description

### Product Perspective
EventSphere is a standalone, web-based client-server application: a Vue.js single-page frontend that communicates with a Node.js/Express REST API backed by a MongoDB database. It integrates with an external payment gateway for payment confirmation.

### Product Functions (High Level)
1. Discover events (homepage, featured events, listing, calendar, search and filters)
2. View complete event details
3. Book standard tickets or VIP packages as a guest or a logged-in customer
4. Pay and receive a confirmed booking
5. Download a printable PDF ticket with a unique QR code
6. Manage a customer profile and booking history (optional account)
7. Producers manage their own events, ticket inventory, and VIP packages
8. Admins manage users, Producers, events, and platform settings
9. Check-in staff scan and validate tickets at the entrance

### User Classes and Characteristics

| User Class | Description | Account Required |
|-----------|-------------|------------------|
| Guest / Customer | Browses events and books tickets. May create an account after purchase. | No (optional) |
| Producer | Creates and manages their own events and packages. | Yes |
| Admin | Manages users, Producers, events, and platform settings. | Yes |
| Authorized Check-in Staff | Scans and validates tickets at event entrances (final access-control design to be confirmed). | Yes |

### Operating Environment
- **Client:** Modern browsers (latest Chrome, Edge, Firefox, Safari) on desktop, tablet, and mobile
- **Server:** Node.js runtime
- **Database:** MongoDB
- **Hosting:** To be decided (cloud or local deployment for demo)

### Planned Technology Stack *(provisional until confirmed by the team)*

| Layer | Technology |
|-------|-----------|
| Frontend | Vue.js |
| Backend | Node.js, Express.js |
| Database | MongoDB |
| UI/UX Design | Figma (optionally Stitch, exported to Figma) |
| Version Control | Git and GitHub |
| Task Management | Trello |

### Assumptions and Dependencies
- Payment is processed through a third-party gateway (provider to be decided; a sandbox/test mode is used during development).
- The backend must confirm payment before a ticket is considered valid.
- The method customers use to access their PDF tickets after purchase (for example, a booking reference lookup or a download link on the confirmation page) is **pending client confirmation**.
- Email ticket delivery is not part of the confirmed scope.
- Event and venue data are entered by Producers or seeded for the demo.

---

## 5. Visual Mockup Reference

- **Figma Mockup (Public):** `<ADD FIGMA LINK HERE>`
- Includes desktop, tablet, and mobile views, plus a style guide component (Typography, Color, Branding).

| Page | Reference Inspiration | Mockup Status |
|------|----------------------|---------------|
| Homepage | Live Nation (Ref #1) | To do |
| Event Listings | Live Nation (Ref #2) | To do |
| Event Calendar | Live Nation (Ref #3) | To do |
| Featured Events | Ticketmaster (Ref #4) | To do |
| Event Details | Ticketmaster (Ref #5) | To do |
| Customer Profile | Ticketmaster (Ref #6) | To do |
| VIP Guide | Ticketmaster (Ref #6) | To do |
| Meet & Greet VIP Packages | Ref #7 | To do |
| Special Access VIP Packages | Ref #8 | To do |
| Checkout / Confirmation / Ticket | Additional page | To do |
| Producer Dashboard, Admin Dashboard, Check-in Scanner | Additional pages | To do |

---

## 6. Features

| ID | Feature | Description |
|----|---------|-------------|
| FEAT001 | Homepage | Immediately highlights upcoming events and featured artists, with a "What's Happening" search by location and date. |
| FEAT002 | Event Listings | Events organized by month and easy to browse so customers do not spend long searching. |
| FEAT003 | Event Calendar | Find events by date, category, and location without scrolling through everything. |
| FEAT004 | Featured Events | Promoted events carousel and banner controlled by Producers/Admin. |
| FEAT005 | Event Details Page | Each event has its own page with complete information (artist, venue, date and time, description, ticket types, VIP packages). |
| FEAT006 | Guest Checkout | Customers can book tickets without creating an account first. |
| FEAT007 | Optional Account Creation | After a successful purchase, customers may create an account that links to their booking. |
| FEAT008 | Customer Profile | Returning customers manage personal information and view booking history in one place. |
| FEAT009 | Standard Tickets and Seat/Inventory Selection | Customers pick ticket type and quantity (and seats where applicable). |
| FEAT010 | VIP Guide Page | Dedicated page for VIP experiences with trending packages and filters by event, artist, and perk type. |
| FEAT011 | Meet & Greet Packages | Packages that include meeting the artist, with limited slots shown clearly. |
| FEAT012 | Special Access Packages | Early entry, lounge access, soundcheck access, and similar perks. |
| FEAT013 | Payment Processing | Payment through a gateway; backend confirms payment before ticket issuance. |
| FEAT014 | PDF Tickets with Unique QR Codes | Printable ticket generated only after confirmed payment. |
| FEAT015 | Ticket Validation / Check-in | Staff scan the QR code; the system validates it and blocks duplicate check-ins. |
| FEAT016 | Producer Event Management | Producers create, edit, and manage their own events, inventory, and VIP packages. |
| FEAT017 | Admin Management | Admins manage users, Producers, events, and platform-level settings. |
| FEAT018 | Responsive Design | Layouts for desktop, tablet, and mobile. |

### Proposed VIP Differentiators (to confirm with the client)
The client asked for a VIP experience that is "even more exciting" than existing platforms. These proposals are candidates, not confirmed scope.

- **Tiered packages:** Bronze/Silver/Gold style tiers shown side by side for easy comparison.
- **Perk checklist:** Each package lists its perks with clear icons so the value is visible at a glance.
- **Limited-slot indicator:** Shows remaining Meet & Greet slots to convey exclusivity.
- **Add-on builder:** Customers add perks (merch bundle, early entry, parking) to a base ticket.
- **VIP digital pass:** The PDF ticket for VIP buyers lists the purchased perks and their redemption status.
- **Waitlist:** Customers can join a waitlist for sold-out VIP packages.

---

## 7. Functional Requirements

### Use Cases

#### UC-01: Browse and Discover Events
- **Title:** Browse and Discover Events
- **Description:** A customer views upcoming and featured events, then searches or filters by keyword, location, date, or category.
- **Actors:** Guest/Customer
- **Preconditions:** None.
- **Postconditions:** Customer can open an event's details page.
- **Main Flow:**
  1. Customer opens the homepage and sees upcoming and featured events.
  2. Customer searches or filters events, or opens the calendar.
  3. System displays matching events.
  4. Customer selects an event to open its details page.
- **Alternate Flows:** No matches found → system shows a "no events found" message with suggested events.

#### UC-02: Book Tickets as a Guest
- **Title:** Book Tickets as a Guest
- **Description:** A customer buys standard tickets or a VIP package without an account.
- **Actors:** Guest/Customer, Payment Gateway
- **Preconditions:** Event is published and has available inventory.
- **Postconditions:** Booking is confirmed, tickets are issued, and inventory is reduced.
- **Main Flow:**
  1. Customer selects ticket type or VIP package and quantity.
  2. System temporarily reserves the inventory.
  3. Customer enters name and contact details.
  4. Customer pays through the payment gateway.
  5. Backend confirms the payment.
  6. System creates the booking, generates tickets with unique QR codes, and shows the confirmation page.
- **Alternate Flows:**
  - Payment fails → booking is not confirmed; reservation is released and the customer may retry.
  - Reservation expires → customer is asked to reselect.
  - Inventory runs out during checkout → customer is notified and offered alternatives.

#### UC-03: Create an Account After Purchase
- **Title:** Optional Account Creation
- **Description:** After a successful booking, the customer may create an account that links the booking to it.
- **Actors:** Guest/Customer
- **Preconditions:** A booking has been confirmed.
- **Postconditions:** An account exists and the booking appears in the booking history.
- **Main Flow:**
  1. Confirmation page offers "Create an account."
  2. Customer sets a password (details prefilled from the booking).
  3. System creates the account and links the booking.
- **Alternate Flows:** Customer declines → booking remains valid as a guest booking. Email already registered → system asks the customer to log in instead.

#### UC-04: Access PDF Ticket
- **Title:** Access PDF Ticket
- **Description:** The customer downloads and prints the ticket.
- **Actors:** Guest/Customer
- **Preconditions:** Payment is confirmed.
- **Postconditions:** Customer has the PDF ticket.
- **Main Flow:** Customer downloads the ticket from the confirmation page (or from booking history if logged in).
- **Alternate Flows:** Guest returns later → access via booking reference lookup *(final method pending client confirmation)*.

#### UC-05: Explore VIP Packages
- **Title:** Explore VIP Packages
- **Description:** A customer views the VIP Guide and compares packages.
- **Actors:** Guest/Customer
- **Preconditions:** At least one active VIP package exists.
- **Postconditions:** Customer can add a package to checkout.
- **Main Flow:** Customer opens the VIP Guide, browses trending, Meet & Greet, and Special Access packages, compares perks, and selects a package.
- **Alternate Flows:** Package is sold out → waitlist option (if approved).

#### UC-06: Manage Events (Producer)
- **Title:** Manage Events
- **Description:** A Producer creates, edits, publishes, and cancels their own events and sets ticket and VIP inventory.
- **Actors:** Producer
- **Preconditions:** Producer is logged in and approved.
- **Postconditions:** Event data is saved and visible according to its status.
- **Main Flow:** Producer opens the dashboard, creates an event with venue, date, description, ticket types, and VIP packages, then publishes it.
- **Alternate Flows:** Validation errors → system highlights the invalid fields. Producer attempts to edit another Producer's event → access denied.

#### UC-07: Administer the Platform (Admin)
- **Title:** Administer the Platform
- **Description:** An Admin manages users, Producers, events, and featured placements.
- **Actors:** Admin
- **Preconditions:** Admin is logged in.
- **Postconditions:** Changes are saved and logged.
- **Main Flow:** Admin approves or suspends Producers, edits or removes events, manages featured events, and reviews bookings.

#### UC-08: Validate Ticket at Check-in
- **Title:** Validate Ticket at Check-in
- **Description:** Staff scan a ticket QR code at the entrance.
- **Actors:** Authorized Check-in Staff
- **Preconditions:** Staff is logged in; ticket was issued for this event.
- **Postconditions:** Ticket status is set to "used."
- **Main Flow:** Staff scans the QR → system verifies the token and event → marks the ticket as used → shows "Valid" along with ticket type (VIP perks if applicable).
- **Alternate Flows:** Already used → "Duplicate check-in" warning. Invalid or wrong event → "Invalid ticket." Cancelled ticket → "Ticket not valid."

### System Features

#### SF-01: Event Search and Filtering
- **Description:** Search by keyword and filter by location, date range, and category.
- **Priority:** High
- **Inputs:** Keyword, location, date range, category.
- **Processing:** Query published events and sort by date.
- **Outputs:** Paginated list of events.
- **Error Handling:** Invalid dates are rejected with a message; empty results show a friendly message.

#### SF-02: Booking and Inventory Control
- **Description:** Create bookings while preventing overselling.
- **Priority:** High
- **Inputs:** Event, ticket type or VIP package, quantity, customer details.
- **Processing:** Reserve inventory, hold for a limited time, finalize after payment confirmation.
- **Outputs:** Booking record and reference number.
- **Error Handling:** Sold-out, expired reservation, and invalid input cases return clear errors.

#### SF-03: Payment Confirmation
- **Description:** Confirm payment before any ticket is valid.
- **Priority:** High
- **Inputs:** Payment gateway response/webhook.
- **Processing:** Backend verifies the payment status and amount, then marks the payment as paid.
- **Outputs:** Payment status update that triggers ticket generation.
- **Error Handling:** Failed or mismatched payments leave the booking unconfirmed; duplicate webhooks are handled idempotently.

#### SF-04: PDF Ticket and QR Generation
- **Description:** Generate a printable PDF ticket with a unique QR code per ticket.
- **Priority:** High
- **Inputs:** Confirmed booking.
- **Processing:** Generate a unique, non-guessable token per ticket, encode it in a QR code, and render the PDF (event, date, venue, ticket type, VIP perks, booking reference).
- **Outputs:** Downloadable PDF.
- **Error Handling:** Generation failure is logged and can be retried without creating duplicate tokens.

#### SF-05: Ticket Validation
- **Description:** Validate tickets at check-in and prevent duplicates.
- **Priority:** High
- **Inputs:** Scanned QR token, event ID.
- **Processing:** Look up the token, verify event and status, atomically mark as used.
- **Outputs:** Valid / already used / invalid result.
- **Error Handling:** Network or scan errors prompt a rescan; concurrent scans of the same ticket allow only one success.

#### SF-06: Role-Based Access Control
- **Description:** Restrict features by role.
- **Priority:** High
- **Inputs:** Authenticated user and role.
- **Processing:** Middleware checks the token and role; Producers can only access their own events.
- **Outputs:** Access granted or denied.
- **Error Handling:** 401 for unauthenticated, 403 for unauthorized requests.

#### SF-07: VIP Package Management and Display
- **Description:** Producers configure VIP packages; customers browse them in the VIP Guide.
- **Priority:** Medium
- **Inputs:** Package name, description, price, perks, slot limit, status.
- **Processing:** Validate, store, and expose active packages per event.
- **Outputs:** VIP Guide listing and package details.
- **Error Handling:** Invalid price or slot values are rejected.

---

## 8. Non-Functional Requirements

### Performance
- Main pages load within 3 seconds on a standard broadband connection.
- Search and filter results return within 2 seconds for typical data volumes.
- Ticket PDF generation completes within 5 seconds.

### Security
- Passwords are hashed (bcrypt); no plain-text storage.
- Authentication with JWT; role-based authorization on every protected endpoint.
- HTTPS for all traffic in production.
- Payment card data is never stored by EventSphere; it is handled by the payment gateway.
- QR tokens are random, unique, and unguessable; validation happens server-side only.
- Input validation and sanitization to protect against injection and XSS; rate limiting on login and checkout endpoints.
- Check-in must prevent duplicate use through an atomic status update.

### Usability
- Consistent navigation and clear calls to action.
- Guest checkout with minimal required fields.
- Responsive layouts for desktop, tablet, and mobile.
- Basic accessibility: readable contrast, labeled form fields, keyboard navigation.

### Reliability
- Target 99% availability during demo and testing.
- Booking and payment operations are consistent: no confirmed ticket without confirmed payment, and no overselling.
- Errors are logged and presented to users with clear messages.

### Supportability
- Code organized by module (routes, controllers, models, services) with consistent naming.
- Documentation maintained in this repository; API documented.
- Changes go through pull requests reviewed by the Team Leader.
- Environment variables used for configuration and secrets.

---

## 9. Data Requirements

### Data Models
Main entities: User (Customer / Producer / Admin / Staff), Venue, Event, VIP Package, Booking, Payment, Ticket, and Seat (optional, only for seated events).

### ERD

> The ERD is shown below using Mermaid (rendered by GitHub). An exported image/link of the ERD: `docs/erd.png`

erDiagram
    USER ||--o{ BOOKING : places
    USER ||--o{ EVENT : produces
    VENUE ||--o{ EVENT : hosts
    VENUE ||--o{ SEAT : contains
    EVENT ||--o{ VIP_PACKAGE : offers
    EVENT ||--o{ BOOKING : receives
    BOOKING ||--|| PAYMENT : paid_by
    BOOKING ||--o{ TICKET : contains
    EVENT ||--o{ TICKET : admits
    SEAT ||--o{ TICKET : assigned_to
    VIP_PACKAGE ||--o{ TICKET : upgrades

    USER {
        ObjectId user_id PK
        string first_name
        string last_name
        string email
        string password_hash
        string phone_number
        string role "customer, producer, admin, staff"
        datetime created_at
    }
    VENUE {
        ObjectId venue_id PK
        string venue_name
        string address
        string city
        int capacity
    }
    EVENT {
        ObjectId event_id PK
        ObjectId venue_id FK
        ObjectId producer_id FK
        string title
        string description
        datetime event_date
        string category
        boolean is_featured
        string status "draft, published, cancelled"
        datetime created_at
    }
    VIP_PACKAGE {
        ObjectId vip_package_id PK
        ObjectId event_id FK
        string package_name
        string package_type "meet_greet, special_access, other"
        string description
        decimal additional_price
        array benefits
        int slot_limit
        boolean is_active
    }
    BOOKING {
        ObjectId booking_id PK
        ObjectId customer_id FK "nullable for guests"
        ObjectId event_id FK
        string guest_name
        string guest_email
        decimal total_amount
        string status "pending, confirmed, cancelled"
        datetime created_at
    }
    PAYMENT {
        ObjectId payment_id PK
        ObjectId booking_id FK
        string method
        decimal amount
        string payment_status "pending, paid, failed, refunded"
        string transaction_ref
        datetime payment_date
    }
    TICKET {
        ObjectId ticket_id PK
        ObjectId booking_id FK
        ObjectId event_id FK
        ObjectId seat_id FK "nullable"
        ObjectId vip_package_id FK "nullable"
        string ticket_type "regular, vip"
        string qr_token "unique"
        decimal price
        string status "reserved, valid, used, cancelled"
        datetime checked_in_at
    }
    SEAT {
        ObjectId seat_id PK
        ObjectId venue_id FK
        string section
        string row
        string seat_number
    }

### Database Requirements
- MongoDB collections: `users`, `venues`, `events`, `vipPackages`, `bookings`, `payments`, `tickets`, `seats`.
- `tickets.qr_token` has a unique index; `users.email` has a unique index.
- `bookings.customer_id` is nullable to support guest checkout; the guest email is stored on the booking.
- Indexes on `events.event_date`, `events.category`, and `events.status` for search.
- Seat availability per event is derived from tickets with status `reserved`, `valid`, or `used`.

### Data Storage and Retrieval
- Data is stored in MongoDB and accessed via Mongoose models through the Express API.
- Generated PDF tickets are produced on demand from ticket data (no permanent file storage required in the current scope).
- Inventory reservations use a short expiry window so abandoned checkouts release their inventory.

---

## 10. External Interface Requirements

### User Interfaces
Responsive web UI (desktop, tablet, mobile) following the Figma mockup and style guide. Main screens: Homepage, Event Listings, Event Calendar, Event Details, VIP Guide, Meet & Greet and Special Access Packages, Checkout, Booking Confirmation and Ticket Download, Customer Profile, Producer Dashboard, Admin Dashboard, and Check-in Scanner.

### API Interfaces
RESTful JSON API (Express). Planned endpoint groups:

| Area | Example Endpoints |
|------|-------------------|
| Auth | `POST /api/auth/register`, `POST /api/auth/login` |
| Events | `GET /api/events`, `GET /api/events/:id`, `POST /api/events` (Producer), `PUT /api/events/:id`, `DELETE /api/events/:id` |
| VIP Packages | `GET /api/events/:id/vip-packages`, `POST /api/vip-packages` (Producer) |
| Bookings | `POST /api/bookings`, `GET /api/bookings/:reference` |
| Payments | `POST /api/payments/checkout`, `POST /api/payments/webhook` |
| Tickets | `GET /api/tickets/:id/pdf`, `POST /api/tickets/validate` (Staff) |
| Admin | `GET /api/admin/users`, `PATCH /api/admin/producers/:id` |

A full API specification will be documented separately.

### Hardware Interfaces
- Device camera (phone, tablet, or webcam) for QR scanning at check-in.
- Printer (optional) for printing PDF tickets.

### Software Interfaces
- Payment gateway (provider TBD; sandbox for development)
- PDF generation library and QR code library (Node.js)
- MongoDB database
- Figma, GitHub, and Trello for design, version control, and task management

---

## 11. Glossary

| Term | Definition |
|------|------------|
| Guest Checkout | Purchasing tickets without an existing account. |
| Producer | A user who creates and manages their own events. |
| Admin | A user who manages the whole platform. |
| Check-in Staff | Authorized personnel who validate tickets at the entrance. |
| VIP Package | A premium add-on or tier with extra perks (for example, Meet & Greet). |
| Meet & Greet | A VIP experience that lets customers meet the artist. |
| Special Access | VIP perks such as early entry, lounge access, or soundcheck access. |
| Featured Event | An event promoted on the homepage. |
| QR Token | A unique, unguessable code embedded in a ticket's QR code. |
| Booking | A customer's confirmed purchase, which can contain multiple tickets. |
| Duplicate Check-in | An attempt to use an already-used ticket. |
| ERD | A diagram showing how data entities relate to one another. |

---

## 12. Appendices

### Supporting Information

**Team and Responsibilities**

| Member | Role | Primary Responsibility |
|--------|------|------------------------|
| Joseph | Team Leader | Project coordination, repository management, requirements consolidation, PR reviews, and integration |
| Loisa | Member | *(to be assigned — suggested: technical specification, authentication and booking)* |
| Gianna | Member | *(to be assigned — suggested: database design/ERD and event management)* |
| Paolo | Member | *(to be assigned — suggested: UI/UX in Figma, payment, PDF tickets, QR validation)* |

All members contribute to documentation, code reviews, testing, and integration. With four members, frontend development and QA/testing are shared across the team.

**Project Links**
- GitHub Repository: `event-booking-system`
- Figma Mockup: `<ADD LINK>`
- ERD: `<ADD LINK>`
- Trello Board (Public, instructor invited; card naming `FEAT000-`): `https://trello.com/invite/b/6adb07aa720e76bb65cfdcc0/ATTIa226ffe861d6aa026bcd43b87d47c99eB1E6085F/eventsphere-event-booking-system`

**Open Items (Pending Client Confirmation)**
1. How customers access their PDF tickets after purchase.
2. Final access-control design for Check-in Staff.
3. Payment provider and supported payment methods.
4. Which proposed VIP differentiators to include.
5. Confirmation of the technology stack by the team.

**Project Status:** Phase 1 — Planning and Documentation

### Revision History

| Version | Date | Author | Description |
|---------|------|--------|-------------|
| 1.0 | October 23, 2026 | Joseph, Loisa, Gianna, Paolo | Initial Technical Specifications Document for the 4-member team |
