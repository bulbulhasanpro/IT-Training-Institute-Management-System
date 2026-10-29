# IT Training Institute Management System (ITIMS)

A PHP + MySQL web application for managing a small IT training institute. Academic final-year project starter.

## Features
- Admin authentication (password hashing and PHP sessions)
- Student and trainer records
- Courses and batches
- Student enrollment
- Attendance tracking
- Payment records and collection summary
- Certificate records
- Dashboard, reports, table search and print support
- Relational database constraints, prepared statements, output escaping and CSRF tokens

## Requirements
- XAMPP with Apache, PHP 8.1+ and MySQL/MariaDB
- Web browser

## Install on Windows using XAMPP
1. Install XAMPP and start **Apache** and **MySQL**.
2. Copy this folder into `C:\xampp\htdocs\itims_project\`.
3. Open `http://localhost/phpmyadmin`.
4. Choose **Import**, select `database.sql`, and run the import. It creates the `itims_db` database and tables. **Warning:** this SQL file drops and recreates tables in `itims_db`; back up existing data first.
5. Open `http://localhost/itims_project/setup.php` once to create the initial admin account.
6. Open `http://localhost/itims_project/login.php`.
7. Sign in with email `admin@itims.local` and password `Admin@123`.
8. Delete or restrict `setup.php` after setup. Change demo credentials before entering real data.

## Default database settings
In `config.php`: host `127.0.0.1`, database `itims_db`, user `root`, password empty. Change these values if your local MySQL setup differs.

## Suggested workflow
1. Add trainers and courses.
2. Create batches (each batch needs a course and trainer).
3. Register students.
4. Enroll students in batches.
5. Record attendance and payments.
6. Add certificate records when learners complete a course.
7. Use Reports and browser Print.

## Project structure
```text
itims_project/
├── assets/style.css
├── assets/app.js
├── config.php
├── database.sql
├── index.php
├── login.php
├── logout.php
├── setup.php
├── README.md
└── PROJECT_REPORT.md
```

## Troubleshooting
- Database connection error: ensure MySQL is running and `config.php` credentials match.
- Unknown table/database: import `database.sql` before running `setup.php`.
- Cannot delete a record: another record may depend on it; remove dependent records first.
- Duplicate code: student IDs, trainer IDs, course codes, batch codes and certificate numbers must be unique. A student can only be enrolled once in the same batch, and attendance can only be recorded once per enrollment per day.
- If the page is blank, check Apache/PHP error logs in XAMPP.

## Academic note
This is an academic starter, not a production-hardened commercial service. Test each feature and capture your own screenshots before submission. Public deployment needs HTTPS, secure credentials, backups, stronger role permissions, audit logging, rate limiting and a security review. The demo admin is intended only for local development.
