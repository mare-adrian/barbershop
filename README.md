
📌 Project Title
Barbershop Appointment Management System
Full Backend Application Using Node.js and Express.js
![image](https://github.com/user-attachments/assets/e510c526-a52a-43fb-a194-f0fc8d228133)


🧾 Overview
This project is a fully functional web-based system developed to manage customer appointments in a barbershop. Built entirely with Node.js and Express.js, the application supports both user-facing features and administrative tools.

Instead of relying on a traditional database, it uses a local JSON file to persist booking data. This design offers a lightweight and efficient solution, ideal for small and medium-sized service businesses.

The system includes:

Calendar-based appointment scheduling

Conflict detection

Admin panel with authentication

Real-time statistics

Structured REST API

Frontend integration via static file serving

🗓️ Main Feature: Calendar-Based Booking System
The heart of this application is an interactive calendar that allows customers to:

View already-booked time slots for a given date

Book a new appointment by selecting a date and time, entering their name and phone number

Submit validated form data (checks include date format, phone format, available hours)

Prevent bookings in the past or outside working hours (09:00–17:00)

This feature helps customers make quick, conflict-free bookings without needing to call or visit the salon.

![image](https://github.com/user-attachments/assets/345d0851-a5f4-48cb-9657-7caaf704fb63)

In the calendar, users can select a date and time to create a booking. Once the booking is successfully submitted, the selected time slot becomes marked as unavailable, preventing others from choosing the same slot.

At the same time, the appointment details are automatically sent to the Admin Hub, where staff members can view and manage all bookings.

It's important to note that all submitted data is carefully validated. For example, the system will not allow a user to enter an invalid phone number. Specifically for Romanian numbers, it enforces a minimum of 10 digits, ensuring the input follows a correct format before the reservation is accepted.

How to make an appoiment:




![image](https://github.com/user-attachments/assets/59ed6c6e-0d9b-49f2-983e-34763c4a2d1c)




How other clients see your appoiment:




![image](https://github.com/user-attachments/assets/7a7fa960-3ac4-4581-b41a-d45cdc4c9a6b)


Admin Panel:
![image](https://github.com/user-attachments/assets/b6d2fb4f-1db1-4696-a58a-8985f1d70cdd)













🔐 Admin Panel Functionality
The admin panel, available at /admin, enables barbershop staff to:

Log in with secure, predefined credentials

View all bookings: daily, weekly, or full history

Update existing appointments (date/time/customer info)

Cancel or delete appointments

View real-time statistics:

Total appointments today

Appointments for the week

Total bookings to date

The admin interface acts as a lightweight CRM system to efficiently manage appointments and daily schedules.
Admin Authentication :
![image](https://github.com/user-attachments/assets/9898b8fa-4152-408d-9103-aebb29c7281f)
The Admin Panel allows barbershop staff to manage all appointments efficiently. Here are the main options available:

Dashboard Statistics

View number of appointments: today, this week, and total.

Filter & Search
Filter by date or search by customer name/phone.

Appointment List
View all bookings in a table with date, time, name, phone, and status.

Edit Appointment
Change time, date, or customer details. Conflicts are automatically checked.

Delete Appointment
Permanently remove a booking and free up the slot.

Refresh Button
Instantly reload all bookings and stats.

Logout(Ends the admin session securely.
You can see the options below:
![image](https://github.com/user-attachments/assets/9e92f586-baeb-4a4d-a649-5afd5feb008f)


🧱 Architecture & Components
1. Server Setup
Built with Express.js

Configured with:

CORS for cross-origin requests

express.json() to parse request bodies

express.static() to serve static frontend files

Automatically creates necessary folders and files at startup

2. Static File Handling
Files in /public/ (e.g. admin.html) are served at root level

No need for a separate frontend server

3. Data Persistence
Booking data stored in data/bookings.json

Uses fs.promises for asynchronous read/write operations

4. Authentication (Admin Login)
Hardcoded admin credentials

Token-based session system with:

24-hour expiration

Memory storage (Map)

Bearer token for protected routes

Auto-purging of expired tokens every hour

5. Booking Functionality (CRUD)
Create Appointment
POST /api/bookings

Validates input, prevents double bookings, assigns unique ID

Read Appointments

GET /api/bookings/:date: Time slots for specific day

GET /api/bookings: All bookings

GET /api/bookings/today: Today’s appointments

GET /api/bookings/week: This week’s appointments

Update Appointment
PUT /api/bookings/:date/:id

Reschedule date/time, with validation and conflict checking

Delete Appointment
DELETE /api/bookings/:date/:id

Deletes appointment; cleans up empty dates from file

6. Validation and Error Handling
Validates phone numbers, name lengths, past-date restrictions

Handles unknown routes with 404 response

Protected routes reject invalid or expired tokens

7. Logging and Debugging
Logs login attempts, errors, and token events to console

Test endpoint: GET /test returns server status and token count

💡 Technologies Used
Node.js & Express.js – Backend framework

File System (fs.promises) – JSON-based persistence

CORS – Cross-origin communication

Crypto – Token generation and session security

Custom Middleware – Auth protection and error handling

This section features a brief description of the barber, along with a “Contact Me” button. When clicked, the button smoothly scrolls the user to the bottom of the page, where the barber’s contact details are displayed (such as phone number, email, or location).

It’s designed to give a quick introduction and make it easy for potential clients to get in touch.










![image](https://github.com/user-attachments/assets/b770d812-0a4f-4325-a4de-fac481a1624e)


🛠 Skills Gained
Technical Skills:
Backend architecture using Express.js

RESTful API design with authentication

Secure token management and session expiration

Input validation and business rule enforcement

File-based data persistence and asynchronous programming

Error handling, logging, and debugging

Soft Skills:
Project planning and feature breakdown

Clean code organization and modular design

Documentation and route clarity

Problem-solving (e.g., time conflict handling, rescheduling logic)

Real-world logic implementation (time slots, scheduling constraints)


This project demonstrates my ability to independently design, build, and maintain a backend application that handles real-world complexity and edge cases. I’ve shown that I can:

Develop secure and scalable backend systems

Integrate APIs with frontend interfaces

Handle and validate user-generated data reliably

Think through both technical and user-experience considerations

Whether in a junior backend or full-stack developer position, Although I am not a professional developer yet, I am highly motivated to learn and grow in this field. This project is a clear demonstration of my commitment, curiosity, and ability to apply what I’ve learned independently.

By building a fully functional appointment management system from scratch using Node.js and Express, I’ve proven that I can understand backend logic, structure a real-world application, and solve problems effectively — even without formal experience.

I'm eager to continue improving my skills and contribute to real development teams in the near future.



Note:
This project was built as a demonstration using a simple Node.js server and local JSON file storage for simplicity and educational purposes. However, the application is fully adaptable to use a real database system (such as MongoDB, PostgreSQL, or MySQL) for production use.

The current architecture separates logic and data handling in a way that makes it easy to replace the file-based storage with database queries, without major changes to the API structure or route behavior.
