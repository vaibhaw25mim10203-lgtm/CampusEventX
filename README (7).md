# CampusEventX — Smart Campus Event & Resource Scheduler

A complete web application that automates university event approvals, venue reservations, and resource scheduling using a **time-slot collision detection engine** and a **multi-role approval workflow**. The system routes every booking request through Faculty Sponsors and Venue Administrators, tracks its status in real time, and prevents double-booked venues automatically.

Built for the **CampusEventX** course project submission.

---

## Overview

CampusEventX manages the full lifecycle of a campus event booking and lets it:

- Reserve venues **without conflicts** using an automated collision-detection algorithm
- Route requests through a **sequential approval pipeline** (Student → Faculty Sponsor → Venue Administrator)
- Track live status updates (`Pending`, `Approved`, `Rejected`) for every booking
- Generate **analytics dashboards** and exportable **PDF receipts/audits**

The system is a full-stack web application with a REST API backend — no manual spreadsheets or email chains required.

---

## Features

| Feature                     | Description                                                                 |
| ---------------------------- | ---------------------------------------------------------------------------- |
| **Role-based access control** | JWT-authenticated roles for Students, Faculty Sponsors, and Venue Admins    |
| **Conflict engine**          | Validates time slot, room capacity, and technical requirements before booking |
| **Approval workflow**        | Sequential, auditable approval pipeline with status tracking                |
| **Analytics dashboard**      | Real-time venue utilization and attendance statistics                       |
| **PDF report generator**     | Exports booking receipts and audit trails as PDFs                           |
| **Centralized logging**      | Winston/Morgan middleware for request logging and error tracking            |
| **Input validation**         | Sanitization against SQL injection and XSS on every endpoint                |

---

## Technologies Used

- **Frontend:** React.js, HTML5, CSS3, JavaScript
- **Backend:** Node.js with Express.js (or Python FastAPI)
- **Database:** PostgreSQL / MongoDB
- **Auth:** JWT + bcrypt password hashing
- **Logging:** Winston / Morgan
- **PDF generation:** PDFKit
- **Testing:** Jest / Mocha
- **Version control:** Git & GitHub

---

## Project Structure

```
CampusEventX/
├── .github/                  # CI/CD actions or workflows
├── docs/                     # Diagrams and architecture specs
├── src/
│   ├── config/               # DB connection & env variables
│   ├── controllers/          # Business logic handlers
│   ├── middleware/           # Auth, logging & validation middlewares
│   ├── models/                # DB schemas / ORM models
│   ├── routes/                # API endpoint definitions
│   ├── services/              # Collision detection & PDF services
│   └── utils/                 # Helper functions
├── tests/                     # Unit tests (Jest/Mocha)
├── .gitignore
├── package.json
├── README.md                  # Complete documentation & setup guide
└── statement.md                # Problem statement, scope & target audience
```

---

## Installation & Setup

### 1. Clone the repository

```bash
git clone https://github.com/<your-username>/CampusEventX.git
cd CampusEventX
```

### 2. Install dependencies

```bash
npm install
```

### 3. Configure environment variables

Create a `.env` file in the project root:

```env
PORT=5000
DATABASE_URL=your_database_url
JWT_SECRET=your_jwt_secret
```

### 4. Run the development server

```bash
npm start
```

---

## How to Run

All commands are run from the project root.

### Start the API server

```bash
npm start
```

### Run in development mode (auto-reload)

```bash
npm run dev
```

### Seed the database (sample users, venues, events)

```bash
npm run seed
```

### Key API endpoints

```
POST   /api/auth/register        # Register a new user (student/faculty/admin)
POST   /api/auth/login           # Log in and receive a JWT
POST   /api/venues                # Create a venue (admin only)
GET    /api/venues/availability  # Check venue availability for a time slot
POST   /api/bookings              # Submit a booking request
PATCH  /api/bookings/:id/approve  # Approve/reject a booking (faculty/admin)
GET    /api/analytics/utilization # Venue utilization analytics
GET    /api/bookings/:id/receipt  # Download a PDF booking receipt
```

---

## Testing

Each module has a dedicated test suite:

```bash
npm test                     # Run the full test suite
npx jest conflictEngine      # Venue collision-detection logic
npx jest auth                # Authentication & RBAC
npx jest bookings            # Booking workflow & approvals
```

All tests report pass/fail counts and coverage in the terminal.

---

## Future Enhancements

- Mobile push notifications for approval status changes
- Calendar sync (Google Calendar / Outlook) for approved events
- Waitlist support for fully booked venues
- Role-based analytics exports (per-department reporting)
- Dockerize the project for one-command deployment

---

## License

Educational project — free to use and learn from.

---

## Author

**[Your Name]** — CampusEventX Course Project
