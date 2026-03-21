# Tutor Booking Platform API

A full-featured backend API for a tutor booking platform supporting students, tutors, and admins. Built with robust authentication, role-based access control, and scalable architecture.

---

# 🚀 Features

## 🔐 Authentication & Authorization

* Email & password sign-up/sign-in (better-auth)
* Email verification via Nodemailer
* Password reset with secure token flow
* Role-based access: **STUDENT**, **TUTOR**, **ADMIN**
* User status: **ACTIVE**, **INACTIVE**, **SUSPENDED**
* Protected routes with middleware

## ⚙️ Error Handling

* Centralized async handler
* Standard response format:

  * Success: `{ success: true, data }`
  * Error: `{ success: false, error: { code, message } }`

---

# 👨‍🎓 Student Features

## Profile

* Create/update profile (class, institute, address, phone, bio, group)
* Profile includes recent bookings & reviews

## Tutors

* Browse tutors with filters:

  * Search (name/subject)
  * Category
  * Group
  * Price range
  * Availability
  * Featured
* View detailed tutor profile

## Categories

* List all categories and subjects

## Bookings

* Create booking (date, time, duration)
* View bookings (filters: status/date)
* Cancel booking (only confirmed)

## Reviews

* Add review after completed session
* One review per booking
* View own reviews

---

# 👨‍🏫 Tutor Features

## Profile

* Manage teaching details (subjects, experience, price, category)
* Availability toggle (on/off)
* Profile includes stats and ratings

## Availability

* Set availability window
* Enable/disable bookings

## Sessions

* View bookings (sessions)
* Filter by status/date/student
* Mark session as completed

## Reviews

* View received reviews with filters

## Dashboard

* Stats:

  * Total / confirmed / completed / cancelled sessions
  * Average rating

---

# 🛠 Admin Features

## User Management

* List/filter users
* Change role & status
* Suspend/activate users
* Delete users (cascade delete)

## Analytics

* Metrics (users, bookings, reviews)
* Booking trends (time series)
* Top tutors ranking

## Moderation

* Delete inappropriate reviews
* Control tutor availability
* Set featured tutors

## Categories

* Create/update/delete categories
* Prevent deletion if in use

---

# 📡 API Overview

## Base Routes

| Route               | Description                  |
| ------------------- | ---------------------------- |
| `/api/auth/*`       | Authentication (better-auth) |
| `/api/v1/student/*` | Student features             |
| `/api/v1/tutor/*`   | Tutor features               |
| `/api/v1/admin/*`   | Admin features               |

## Public Endpoints

* `GET /api/v1/student/tutors`
* `GET /api/v1/student/tutors/:id`
* `GET /api/v1/student/categories`

## Protected Routes

* Require authentication session
* Role-based access enforced

---

# 🧠 Roles Summary

| Role    | Access                                 |
| ------- | -------------------------------------- |
| Student | Booking, reviews, tutor browsing       |
| Tutor   | Manage sessions, profile, availability |
| Admin   | Full system control                    |

---

# 🧩 Tech Stack

* Node.js + Express
* Prisma ORM
* better-auth
* Nodemailer
* TypeScript

---

# 📌 Notes

* Only verified users can access protected features
* Tutors must be available to receive bookings
* Reviews require completed sessions

---

# 📬 Future Improvements

* Payment integration
* Real-time chat
* Notification system
* Advanced tutor ranking algorithm

---

> Clean, scalable, and production-ready backend for a tutor marketplace 🚀
