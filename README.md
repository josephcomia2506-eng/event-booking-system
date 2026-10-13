# EventSphere — Event Booking and VIP Experience System

## Project Overview

EventSphere is a web-based event booking system designed to help
customers discover events, book tickets, and explore exclusive VIP
experiences such as Meet & Greet packages.

The system also provides event management tools for Producers and
administrative controls for the Admin.

## Problem Statement

Customers need a convenient way to discover upcoming shows, review
event details, and book tickets. Event organizers also need a system
to manage events, ticket availability, and exclusive VIP packages.

EventSphere aims to bring these features together in one platform.

## Project Objectives

- Provide an engaging interface for discovering upcoming and featured events.
- Allow customers to book tickets without creating an account beforehand.
- Support optional account creation after a successful purchase.
- Provide standard tickets and configurable VIP packages.
- Allow Producers to manage their own events.
- Allow Admins to manage the overall platform.
- Generate printable PDF tickets with unique QR codes after payment confirmation.
- Validate tickets securely during event check-in.

## User Roles

1. **Guest/Customer** — Browses events and books tickets without
   requiring an account before checkout.
2. **Producer** — Creates and manages their own events, subject to
   the permissions defined by the system.
3. **Admin** — Manages users, Producers, events, and other
   administrative functions.
4. **Authorized Check-in Staff** — Scans and validates tickets
   at event entrances, subject to the final access-control design.

## Planned Technology Stack

- Frontend: Vue.js
- Backend: Node.js and Express.js
- Database: MongoDB
- UI/UX Design: Figma
- Version Control: Git and GitHub
- Task Management: Trello

*The technology stack is provisional until confirmed by the team.*

## Team Members and Responsibilities

| Member | Primary Responsibility |
|---|---|
| Member 1 — Team Leader | Project coordination, repository management, requirements consolidation, and integration |
| Member 2 | Technical specification and authentication/booking |
| Member 3 | Database design and event management |
| Member 4 | UI/UX, payment, PDF tickets, and QR validation |
| Member 5 | Frontend and QA/testing |

All members contribute to documentation, code reviews, testing, and integration.

## Project Documentation

- [Technical Specification](docs/technical-specification.md)
- [Requirements](docs/requirements.md)
- [Database Design](docs/database-design.md)
- [API Specification](docs/api-specification.md)
- [QA Test Plan](docs/qa-test-plan.md)
- [Meeting Notes](docs/meeting-notes.md)
- [Revision History](docs/revision-history.md)

## Project Status

**Current Phase:** Phase 1 — Planning and Documentation

## Important Notes

- Customers must be able to purchase tickets without creating an account first.
- Account creation after a successful purchase is optional.
- The backend must confirm payment before a ticket is considered valid.
- Each ticket must have a unique QR code or token.
- Ticket validation must prevent duplicate check-ins.
- The method customers will use to access their PDF tickets after
  purchase remains subject to client confirmation.
- Email ticket delivery is not included in the current confirmed scope.