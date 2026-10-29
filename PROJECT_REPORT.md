# IT Training Institute Management System (ITIMS)
## Final-Year Project Report — Draft

**Department:** Computer Science and Engineering  
**Technology:** PHP, MySQL, HTML, CSS, JavaScript  
**Project type:** Web-based information management system

*Before submission, add your university-required cover page, supervisor details, implementation screenshots, and actual test results.*

## Abstract
The IT Training Institute Management System (ITIMS) is a web application designed to organize administrative work in a computer and IT training institute. It centralizes student registration, trainer records, courses, batches, enrollment, attendance, payments and certificate records. PHP handles server-side requests and MySQL stores structured information. The dashboard and reports help an administrator review institute activity. The application includes baseline safeguards such as password hashing, prepared statements, output escaping and CSRF tokens.

## 1. Introduction
Institutes may keep student details, attendance and payment records in paper registers or separate spreadsheets. Such processes can make searching, reporting and maintaining consistent information difficult. ITIMS provides one browser-based interface and relational database for common administrative tasks.

## 2. Problem statement
Manual or disconnected record keeping may cause duplicate information, slow reporting, difficulties tracking attendance and unclear fee histories. A centralized system can improve consistency and reduce repetitive administration.

## 3. Objectives
1. Maintain student and trainer information.
2. Manage courses, batches and trainer assignments.
3. Enroll students in training batches.
4. Record attendance by enrollment and date.
5. Store payments against an enrollment.
6. Track certificate records.
7. Present summary reports for enrollment, attendance and payments.
8. Apply basic web security practices.

## 4. Scope
The current academic version supports administrator login and create, view, update and delete operations for students, trainers, courses, batches, enrollments, attendance, payments and certificates. Reports show enrollment by course, attendance counts and monthly payment totals. Online payment gateways, SMS, student self-service and PDF certificate generation are future enhancements.

## 5. Technology stack
- Frontend: HTML5, CSS3 and JavaScript
- Backend: PHP 8.1+
- Database: MySQL or MariaDB with InnoDB
- Local server: Apache through XAMPP
- Tools: code editor, web browser and phpMyAdmin

## 6. Functional requirements
- Administrator can log in and log out.
- Student, trainer and course records can be maintained.
- Each batch references an existing course and trainer.
- Each enrollment references an existing student and batch.
- Attendance is linked to an enrollment and date.
- Payments are linked to an enrollment.
- Certificates are linked to enrollments and have unique certificate numbers.
- Dashboard and reports display aggregate operational information.

## 7. Non-functional requirements
- Usability: clear navigation and responsive forms.
- Integrity: foreign keys protect relational consistency.
- Security baseline: password hashes, session authentication, prepared statements, output escaping and CSRF tokens.
- Maintainability: modules share common configuration and CRUD patterns.
- Portability: works on a system with PHP and MySQL configured.

## 8. System modules
1. Authentication
2. Dashboard
3. Student management
4. Trainer management
5. Course management
6. Batch management
7. Enrollment management
8. Attendance management
9. Payment management
10. Certificate management
11. Reporting

## 9. Database design
The database contains users, students, trainers, courses, batches, enrollments, attendance, payments and certificates.

Relationships:
- One course can have many batches.
- One trainer can be assigned to many batches.
- One student can have many enrollments.
- One batch can have many enrollments.
- One enrollment can have multiple attendance records and payments.
- One enrollment can have at most one certificate in this version.

Primary keys identify rows; foreign keys and unique constraints help prevent orphan records and duplicates.

## 10. Workflow
1. Administrator signs in.
2. Trainers and courses are entered.
3. A batch is created with a course and trainer.
4. Students are registered and enrolled.
5. Attendance and fee payments are recorded.
6. A certificate record may be added when the course is completed.
7. Reports can be viewed or printed.

## 11. Security considerations
The system uses `password_hash()` and `password_verify()`, PHP sessions, PDO prepared statements, `htmlspecialchars()` output escaping, session ID regeneration at login and CSRF tokens on POST forms. Before public deployment, add password change/reset, granular role authorization, rate limiting, audit logging, HTTPS, backups, secrets management and a formal security review. Never use the demo password for real records.

## 12. Testing plan
Run these tests in your local environment and record the actual result before submission.

| Test | Expected result |
|---|---|
| Correct admin login | Dashboard opens |
| Incorrect login | Error appears |
| Create student | Student appears in list |
| Create batch without course/trainer | Required-field validation prevents submission |
| Enroll same student in same batch twice | Database rejects duplicate enrollment |
| Record attendance twice for same enrollment/date | Database rejects duplicate attendance |
| Record payment | Payment appears in report totals |
| Delete a referenced course | Database prevents deletion while batches depend on it |
| Search a list | Rows filter by entered text |
| Print report | Browser print dialog opens |

## 13. Limitations
This version provides an administrator-focused interface, but no separate student or trainer portal, payment gateway, PDF certificate output, automated notifications or comprehensive role permissions. Certificate eligibility should be enforced by additional business rules in a future version.

## 14. Future enhancements
- Separate admin, trainer, accountant and student roles
- Password reset and change flow
- PDF certificates with verification IDs or QR codes
- Attendance percentage and progress reports
- Fee installments, balances and printable receipts
- Email/SMS notifications
- CSV export and dashboard charts
- Automated backups and audit logs
- Student portal

## 15. Conclusion
ITIMS demonstrates how a PHP application and relational database can support core training-institute workflows. It provides a foundation for student, course, batch, attendance, payment and certificate management. Additional testing, validation, permissions and deployment hardening are needed before real-world use.

## References
1. PHP Manual: https://www.php.net/manual/en/
2. MySQL Reference Manual: https://dev.mysql.com/doc/
3. MDN Web Docs: https://developer.mozilla.org/
4. OWASP Cheat Sheet Series: https://cheatsheetseries.owasp.org/

## Appendix
Follow the steps in `README.md` to run the project locally. Add real screenshots and completed test results from your own running installation.
