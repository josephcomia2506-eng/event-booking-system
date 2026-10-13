# EventSphere — Diagrams

This directory contains the diagrams used to document the system architecture, database structure, and user workflows of the EventSphere Event Booking and VIP Experience System.

The diagrams will be updated as the project requirements and technical design are finalized.

## 1. Entity Relationship Diagram (ERD)

**Purpose:** Illustrates the database entities, their attributes, and the relationships between them.

The planned database entities may include:

- Users and roles
- Producers
- Events and venues
- Ticket types and ticket inventory
- Bookings and booking items
- Payments
- Digital tickets and QR codes
- Ticket validation and check-in records
- VIP packages

**Diagram:** To be added.

**Primary Owner:** Loisa — Database Design

**Status:** Pending

## 2. System Architecture Diagram

**Purpose:** Shows the main system components and how they communicate with one another.

The proposed architecture includes:

- **Frontend:** Vue.js
- **Backend:** Node.js and Express.js
- **Database:** MongoDB
- **Payment Integration:** Payment provider to be confirmed
- **Ticket Generation:** PDF generation and unique QR code creation
- **Ticket Validation:** Backend verification during event check-in

**Diagram:** To be added.

**Primary Owner:** Joseph — Team Leader, coordinating with the team

**Status:** Pending

## 3. User Flow Diagrams

**Purpose:** Illustrates the steps users follow when interacting with the system.

Planned user flows include:

### Customer Booking Flow

1. Browse upcoming and featured events.
2. Select an event and review its details.
3. Choose a ticket type or VIP package.
4. Enter the required customer information.
5. Complete the payment process.
6. Wait for payment confirmation.
7. Access the printable PDF ticket with its unique QR code.
8. Optionally create an account after a successful purchase.

### Ticket Check-in Flow

1. Authorized staff scans the ticket QR code.
2. The system verifies the ticket using the backend.
3. The system checks the ticket's payment status and validity.
4. If valid and unused, the ticket is accepted and marked as used.
5. If invalid, cancelled, refunded, or already used, the system rejects the ticket.

### Producer Flow

1. Producer logs in using an account created by the Admin.
2. Producer views and manages their own events.
3. Producer creates or updates event information.
4. Producer monitors ticket availability for their events.

### Admin Flow

1. Admin logs in.
2. Admin manages users and Producer accounts.
3. Admin oversees events and platform operations.
4. Admin performs authorized administrative actions.

**Diagram:** To be added.

**Primary Owner:** All members, with coordination from the Team Leader

**Status:** Pending

## Diagram File Guidelines

- Save diagram source files and exported images in this directory.
- Use descriptive filenames, such as `erd.png`, `system-architecture.png`, and `customer-booking-flow.png`.
- Where possible, keep editable source files alongside exported PNG or PDF versions.
- Update the links in this README when the diagrams are available.
- Ensure that the diagrams remain consistent with the Technical Specification Document, Requirements Document, and Database Design Document.

## Important Notes

- The diagrams are preliminary until reviewed and approved by the team.
- The final payment provider and payment workflow are subject to confirmation.
- The method customers will use to access their PDF tickets after purchase is still to be confirmed.
- Email ticket delivery is not included in the current confirmed project scope.
- Ticket validation must prevent duplicate check-ins.

## Revision History

| Version | Date | Description |
|---|---|---|
|  |  |  |