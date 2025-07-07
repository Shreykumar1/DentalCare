# ENTNT Dental Center Management Dashboard

## Role: Frontend Developer (React) - Technical Assignment

---

## Project Overview
This is a Dental Center Management Dashboard built for the ENTNT technical assignment. The application allows Admins (Dentists) to manage patients, appointments (incidents), and upload treatment records, while Patients can view their own data and appointment history. All data is simulated and persisted in the browser using localStorage. No backend or external APIs are used.

You can access the app here: [https://dentalcareent.netlify.app](https://dentalcareent.netlify.app)


---

## Table of Contents
- [Features](#features)
- [Setup & Installation](#setup--installation)
- [Architecture](#architecture)
- [Technical Decisions](#technical-decisions)
- [Known Issues & Limitations](#known-issues--limitations)
- [Deployment](#deployment)
---

## Features

### User Authentication (Simulated)
- Hardcoded users with roles: Admin (Dentist), Patient
- Login with email/password
- Session persistence via localStorage
- Role-based access control

### Patient Management (Admin-only)
- View, add, edit, and delete patients
- Patient fields: full name, DOB, contact info, health info

### Appointment / Incident Management (Admin-only)
- Manage multiple incidents per patient
- Fields: title, description, comments, appointment datetime
- After appointment: add cost, treatment, status, next date, and upload files (invoices, images)

### Calendar View (Admin-only)
- Monthly/weekly view of upcoming appointments
- Click a day to view scheduled treatments

### Dashboard (Landing Page)
- KPIs: next 10 appointments, top patients, pending/completed treatments, revenue, etc.

### Patient View (Patient role)
- View only their own data
- Upcoming appointments and history with cost, treatment, and file attachments

### Data Persistence
- All data stored in localStorage
- File uploads saved as base64

### Responsive Design
- Fully responsive across devices

---

## Setup & Installation

### Prerequisites
- Node.js (v18+ recommended)
- npm (v9+ recommended)

### Getting Started
```sh
# 1. Clone the repository
git clone https://github.com/Shreykumar1/DentalCare.git
cd DentalCare

# 2. Install dependencies
npm install

# 3. Start the development server
npm run dev

# 4. Open the app in your browser
# Visit http://localhost:8080 (or the port shown in your terminal)
```

### Build for Production
```sh
npm run build
```

### Linting
```sh
npm run lint
```

---

## Architecture

- **React (Vite + TypeScript):** Modern, fast, and type-safe frontend stack.
- **Routing:** React Router DOM for navigation and route protection.
- **State Management:** React Context API for authentication and app state.
- **Styling:** Tailwind CSS for utility-first, responsive design.
- **UI Components:** shadcn-ui and Radix UI primitives for accessible, reusable UI.
- **Data Persistence:** All data (users, patients, incidents, files) is stored in localStorage. File uploads are saved as base64 or blob URLs.
- **Form Handling:** React Hook Form for form state and validation.
- **Notifications:** Toasts for user feedback (actions, errors, etc).


## Technical Decisions

- **No Backend:** All data is simulated and persisted in localStorage to comply with assignment requirements.
- **Role-based Routing:** ProtectedRoute component ensures only authorized users can access certain routes.
- **Hardcoded Users:** User credentials and roles are hardcoded for demo purposes.
- **File Uploads:** Files are read as base64 and stored in localStorage, allowing preview and download without a backend.
- **UI Library:** shadcn-ui and Radix UI were chosen for accessible, modern, and customizable components.
- **Form Validation:** React Hook Form and Zod are used for robust form validation and error handling.
- **Responsive Design:** Tailwind CSS ensures the app works well on all device sizes.
- **No External Auth/Data Libraries:** All authentication and data logic is implemented manually.

---

## Known Issues & Limitations

- **localStorage Limit:** Browsers have a storage limit (~5MB); large file uploads may fail or be truncated.
- **No Real Backend:** All data is lost if localStorage is cleared. No real user authentication or data persistence beyond the browser.
- **File Security:** Files are stored as base64 in localStorage, which is not secure for sensitive data.
- **No Email/Password Reset:** User management is limited to hardcoded users; no registration or password reset.
- **Simulated Workflows:** Some features (e.g., appointment reminders, notifications) are simulated and not production-ready.

---

## Deployment

The app can be deployed to Vercel, Netlify, or GitHub Pages.

