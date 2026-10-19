# Report 1: Project Description Report

**Kigali Independent University (ULK)** | UML Class Diagram Modelling Assignment

| | |
|---|---|
| **Project title** | Hotel Reservation Management System (HRMS) |
| **Instructor** | Eric Maniraguha |
| **Group member 1** | Ali Amin, Student ID: 202512480 |
| **Group member 2** | Eihassan Ismail, Student ID: 202513493 |
| **Release date** | Thursday, 15 October 2026 |
| **Submission deadline** | Tuesday, 20 October 2026, 8:30 AM |

---

## 1. Project Title and Business Idea

**Project title:** Hotel Reservation Management System (HRMS).

**Business idea:** A small or medium-sized hotel needs an information system to manage its guests, rooms, reservations, payments, additional services, and guest reviews in one place. The system replaces paper registers and scattered spreadsheets with a single, consistent model of how the hotel operates.

## 2. Problem Statement and Purpose

**Problem statement.** Many small hotels still record bookings on paper or in spreadsheets. This leads to double bookings of the same room, lost or unrecorded payments, no reliable view of which rooms are free on a given date, slow check-in and check-out, and no structured way to collect guest feedback.

**Purpose.** The proposed system centralises guest, room, reservation, payment, and service information, prevents booking conflicts, calculates the total cost of a stay automatically, and gives hotel staff and guests a clear process for booking and managing stays. In this assignment the purpose is to analyse these requirements and express them as a UML class model.

## 3. Project Scope

The project focuses on designing the system using a UML class diagram. Developing a working application is not required.

| Functions covered (in scope) | Functions excluded (out of scope) |
|---|---|
| Guest registration and profile management | A fully working application or source code (design only) |
| Management of rooms and room types (Single, Double, Suite) | Complete hotel accounting and tax reporting |
| Searching for available rooms for given dates | Booking through third-party websites (e.g. Booking.com) |
| Creating, confirming, and cancelling reservations | Inventory, procurement, and supplier management |
| Check-in and check-out handled by hotel employees | Staff payroll and human-resource management |
| Payments and refunds linked to reservations | Online payment gateway integration |
| Additional services (breakfast, laundry, transport) | Housekeeping scheduling and maintenance management |
| Guest reviews of a completed stay | Marketing campaigns and loyalty programmes |

## 4. Main Classes and Their Responsibilities

| Class | Responsibility |
|---|---|
| Person (abstract) | Holds data common to every individual in the system: ID, full name, email, phone. Parent of Guest and Employee. |
| Guest | A customer of the hotel. Registers, makes and cancels reservations, and writes reviews. |
| Employee | A member of hotel staff. Logs in, confirms reservations, and performs check-in and check-out. |
| Hotel | Represents the hotel itself: name, address, star rating. Owns its rooms and employs its staff. |
| RoomType | Defines a category of room (Single, Double, Suite) with its price per night and capacity. |
| Room | A physical room with a number, floor, and status. Reports whether it is available. |
| Reservation | The booking record: dates, status, and total amount. Can be confirmed, cancelled, and priced. |
| Payment | A payment or refund made against a reservation, with amount, date, method, and status. |
| Service | An extra service the hotel offers (breakfast, laundry, transport) with its price. |
| ServiceOrder | Links a reservation to a service and records quantity and date. Resolves the many-to-many relationship between Reservation and Service. |
| Review | A guest's rating and comment about a reservation. |

## 5. System Requirements

### 5.1 Functional requirements

- **FR1:** A guest can register and maintain a profile.
- **FR2:** A guest can search for available rooms and make a reservation for chosen dates.
- **FR3:** A guest can cancel a reservation.
- **FR4:** An employee can confirm a reservation and perform check-in and check-out.
- **FR5:** The system calculates the total cost of a reservation (price per night multiplied by the number of nights, plus ordered services).
- **FR6:** The system records payments and refunds against a reservation.
- **FR7:** A guest can order additional services during a stay.
- **FR8:** A guest can submit one review for a reservation.

### 5.2 Non-functional requirements

- **Usability:** simple screens that hotel staff can learn quickly.
- **Security:** guest personal data must be protected and only accessible to authorised users.
- **Performance:** availability searches and bookings should respond quickly.
- **Reliability:** reservation and payment records must remain consistent and must not be lost.

### 5.3 Business rules

- A room cannot be reserved twice for overlapping dates.
- The check-out date must be after the check-in date.
- A reservation must belong to one registered guest and include at least one room.
- Each room has exactly one room type; each payment belongs to exactly one reservation.
- A reservation can have at most one review.
