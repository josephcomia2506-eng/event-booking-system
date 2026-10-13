# EventSphere Requirements Document

## 1. Purpose

Document the functional and non-functional requirements of EventSphere.

## 2. User Roles

- Guest/Customer
- Producer
- Admin
- Authorized Check-in Staff

## 3. Functional Requirements

### FR-001: Browse Events
Customers can browse upcoming shows and featured events.

### FR-002: View Event Details
Customers can view event descriptions, dates, venues, ticket prices,
and available ticket categories.

### FR-003: Guest Checkout
Customers can begin the booking process without creating an account.

### FR-004: Customer Information
During checkout, customers provide their first name, last name,
mobile number, and email address.

### FR-005: Optional Account Creation
After a successful purchase, customers can choose whether to create
an account using a password.

### FR-006: Payment Confirmation
The backend verifies the payment result before issuing a valid ticket.

### FR-007: Printable PDF Ticket
After payment confirmation, the system generates a printable PDF ticket.

### FR-008: QR Ticket Validation
Each ticket has a unique QR code or token that authorized staff can
validate against the server.

### FR-009: Duplicate Check-in Prevention
A ticket that has already been used cannot be accepted for another entry.

### FR-010: Producer Event Management
Producers can create and manage their own events, subject to the
permissions and approval workflow agreed upon with the client.

### FR-011: Administrative Management
Admins can manage the system's users, Producers, and events.

## 4. Non-Functional Requirements

- Security
- Performance
- Usability
- Reliability
- Responsive design
- Data integrity
- Maintainability

## 5. Open Questions

- Which payment provider will be used?
- How will customers access their PDF tickets after purchase?
- Will Admin approval be required before an event is published?
- What booking and customer information may Producers access?
- What are the cancellation and refund policies?
- What are the approved VIP package inclusions?