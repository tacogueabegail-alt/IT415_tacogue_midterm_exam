IC LabReserve — Computer Laboratory Reservation System

A frontend-only Computer Laboratory Reservation System for the Institute of Computing. The system replaces informal laboratory booking by allowing teachers to submit laboratory reservations and coordinators to manage reservation requests.

Features

Teacher and Coordinator roles

Create laboratory reservations

Automatic Pending status for new reservations

Laboratory seat-capacity validation

Double-booking prevention

Coordinator approval and rejection

Required rejection reason

Reservation cancellation

Reservation status management

Laboratory schedule by date and laboratory

Reservation search and filtering

Coordinator dashboard with reservation statistics

Clear success and error notifications

In-memory/mock data

No external database required

Laboratory Capacities

Laboratory

Maximum Seats

ComLab 1

40

ComLab 2

30

AES

25

User Roles

Teacher

Teachers can:

Create reservations

View their reservations

View the laboratory schedule

Cancel their own Pending or Approved reservations

Teachers cannot:

Approve reservations

Reject reservations

Cancel another teacher's reservation

Coordinator

The Coordinator can:

View all reservations

Approve Pending reservations

Reject Pending reservations

Enter a reason when rejecting a reservation

Cancel Pending or Approved reservations

View the complete laboratory schedule

View the dashboard

Search and filter reservations

Reservation Status Flow

New reservations begin as:

Pending

Possible transitions:

Pending
 ├──> Approved
 ├──> Rejected
 └──> Cancelled

Approved
 └──> Cancelled

Rejected and Cancelled reservations cannot be changed again.

Double-Booking Prevention

The system checks for overlapping reservations before accepting a new reservation.

A reservation is considered conflicting when it has:

The same laboratory

The same date

An overlapping time period

A status of Pending or Approved

Rejected and cancelled reservations do not occupy the laboratory schedule.

The Coordinator also performs the conflict check again before approving a pending reservation.

Seat-Capacity Validation

The number of students cannot exceed the selected laboratory's capacity.

For example:

ComLab 1 → maximum of 40 students

ComLab 2 → maximum of 30 students

AES → maximum of 25 students

If the requested number exceeds the capacity, the reservation is not submitted.

Technology

This system is designed as a lightweight frontend prototype.

HTML

CSS

JavaScript

In-memory JavaScript arrays/objects

No database

No backend required

Running the System

Because the system is frontend-only, no server or database setup is required.

Download or clone the project.

Open the main HTML file in a modern web browser.

Select the desired user role.

Use the system according to the permissions of that role.

Data Storage

Reservation data is stored in memory using JavaScript.

This means:

No database is required.

No external API is required.

No server is required.

Data is reset when the page/application is refreshed.

The mock reservation data included in the system is intended for demonstration and testing.

Main System Workflow

Teacher Workflow

Select Teacher
      ↓
Create Reservation
      ↓
Validate Laboratory Capacity
      ↓
Check Double Booking
      ↓
Reservation Created
      ↓
Pending
      ↓
Coordinator Reviews
      ↓
Approved / Rejected / Cancelled

Coordinator Workflow

Select Coordinator
      ↓
View Dashboard / Reservations
      ↓
Review Pending Reservation
      ↓
Double-Booking Check
      ↓
Approve or Reject
      ↓
If Rejected → Enter Rejection Reason

Project Scope

This version is intended as a frontend/local prototype of the Institute of Computing laboratory reservation process.

Authentication is represented through the selected application role rather than a real account-management system. Since there is no database or backend, role enforcement is implemented on the client side.

For a production deployment, authentication, authorization, persistent storage, and server-side validation should be added.

File Structure

The project can remain as a single HTML file containing the system's:

HTML interface

CSS styling

JavaScript functionality

The README.md documents the project and does not require a separate backend or database.

Project Purpose

The purpose of IC LabReserve is to provide a structured way for the Institute of Computing to manage computer laboratory reservations while preventing conflicting laboratory schedules and providing a clear approval workflow between teachers and the laboratory coordinator.
