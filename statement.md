# CampusEventX — Project Statement

## Problem Statement

University event management currently relies on manual approval chains and fragmented spreadsheets. Student organizers submit requests over email, faculty sponsors sign off informally, and venue administrators track bookings in separate systems. This leads to double-booked venues, slow and inconsistent approval delays, and no real-time visibility into how campus spaces are actually being used.

There is a need for a system that **automatically validates venue availability** and **tracks every request through a transparent, auditable approval pipeline**.

## Scope

CampusEventX is a **full-stack web application** for managing campus events and venue bookings end to end, with a built-in conflict-detection engine and multi-role approval workflow.

**In scope:**

- Role-based access control for Students, Faculty Sponsors, and Venue Administrators
- Time-slot collision detection validating room capacity, technical requirements, and availability
- Sequential approval workflow with live status tracking (Pending, Approved, Rejected)
- Analytics dashboard for venue utilization and attendance statistics
- PDF export of booking receipts and audit trails

**Out of scope:**

- Payment processing for paid events
- Native mobile applications (mobile-responsive web only)
- Integration with third-party ticketing platforms
- Real-time video/streaming support for events

## Target Users

1. **Students / Event Leads** — Submit event proposals and reserve venues.
2. **Faculty Sponsors** — Review and approve preliminary event proposals.
3. **Venue Administrators** — Manage room allocations, institutional resources, and final approvals.

## High-Level Features

| # | Feature                        | Description                                                                 |
| --- | ------------------------------- | ----------------------------------------------------------------------------- |
| 1 | Authentication & RBAC           | JWT-based login with Student, Faculty Sponsor, and Venue Admin roles         |
| 2 | Conflict Engine                 | Validates time slot, capacity, and equipment before confirming a booking     |
| 3 | Approval Workflow                | Routes requests from Faculty Sponsor to Venue Admin with status updates      |
| 4 | Analytics Dashboard              | Tracks venue utilization rates and attendance statistics in real time        |
| 5 | PDF Report Generator             | Exports booking receipts and audit-ready PDFs                                |
| 6 | Centralized Logging & Errors    | Winston/Morgan middleware with standardized JSON error responses             |
| 7 | Input Validation & Security     | bcrypt password hashing and sanitization against SQL injection / XSS         |
