# Football Ticket Booking System
A database project designed to manage football match ticket bookings, including users, matches, and transactions with proper constraints and relationships.

#### ERD diagram link: https://drive.google.com/file/d/1p0WSvtReDYKCSwXTje-tR6YjPx_w6Jq4/view?usp=sharing

## Database Schema

### 1. Users Table

Stores information about system users.

| Field | Description |
|------|-------------|
| user_id | Unique identifier for each user |
| full_name | Name of the user |
| email | Unique email address |
| role | User role (Ticket Manager / Football Fan) |
| phone_number | Contact number |

---

### 2. Matches Table

Stores football match details.

| Field | Description |
|------|-------------|
| match_id | Unique match identifier |
| fixture | Teams playing (e.g., Team A vs Team B) |
| tournament_category | League or tournament name |
| base_ticket_price | Starting ticket price |
| match_status | Availability status of tickets |

---

### 3. Bookings Table

Stores ticket booking transactions.

| Field | Description |
|------|-------------|
| booking_id | Unique booking ID |
| user_id | References Users table |
| match_id | References Matches table |
| seat_number | Assigned seat (e.g., A-12) |
| payment_status | Payment state (Pending, Confirmed, Cancelled, Refunded) |
| total_cost | Final ticket cost |

---

## 🔗 Relationships

- A **User** can place multiple **Bookings** over time (One-to-Many relationship).
- A **Match** can have multiple **Bookings**, as many users can book tickets for the same match (One-to-Many relationship).
- Each **Booking** is associated with exactly one **User** and one **Match**, ensuring traceability of every transaction.

---

## 🛡️ Constraints Used

- Primary Keys for unique identification
- Foreign Keys to maintain relationships
- UNIQUE constraint on email
- CHECK constraints for:
  - Valid roles
  - Non-negative ticket prices
  - Valid payment statuses

---

## 🧠 Tech Stack

- SQL (PostgreSQL)
---
---
