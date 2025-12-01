# online-library-sys
1. Project Overview
This project is a simple, secure web application designed to manage user accounts and maintain
a digital library collection. It was built with a focus on implementing fundamental security
measures and robust database connectivity.

2. Technologies Used
• Backend: PHP (Native)
• Database: MySQL
• Frontend: HTML5, CSS3, Bootstrap 5 (Dark Theme)
• Environment: XAMPP/WAMP (Local Development) |Shared Hosting (InfinityFree)

3. Key Features
The system offers distinct functionalities based on user roles:

General Users (Role: user)
• Secure Registration & Login (using password hashing).
• View Books List (read-only access).
• Search books by Title or Author.
• Read linked PDF files (if available).

Administrators (Role: admin)
• All user functionalities, plus:
• Add New Books (including cover images and PDF files).
• Edit existing book details.
• Delete books from the library.

4. Database Structure and Setup
The system relies on a MySQL database with two primary tables:

A. users Table
<img width="678" height="329" alt="image" src="https://github.com/user-attachments/assets/afb48bdc-81af-4c8d-aba7-36ac3cfa37df" />


B. books TableColumnTypeDescriptionidINT (PK, AI)Unique Book IdentifiertitleVARCHAR(255)Book title (NOT NULL)authorVARCHAR(255)Book authordescriptionTEXTBook summary/descriptioncover_pathVARCHAR(255)File path for the cover imagepdf_pathVARCHAR(255)File path for the full PDF contentcreated_atTIMESTAMPDate and time of entry




5. Security Measures and Best PracticesSQL Injection Prevention: All database operations (INSERT, SELECT, UPDATE, DELETE) use Prepared Statements with mysqli::prepare() and parameter binding.Password Hashing: User passwords are encrypted using password_hash(PASSWORD_DEFAULT).Role-Based Access Control (RBAC): Access to administrative files (add_book.php, edit_book.php) is protected by checking $_SESSION['user_role'].Input Sanitization: User inputs are stripped of unwanted characters using trim() and secured using htmlspecialchars().6. Installation and ConfigurationTo run the project locally or on a server, follow these steps:6.1. Database SetupCreate a new MySQL database (e.g., online_library).Import the SQL structure (CREATE TABLE statements) into your database.Manually change a user's role from 'user' to 'admin' in the database to gain administrative access.6.2. Code ConfigurationOpen the db.php file.Update the following connection variables with your actual database credentials:PHP$host = 'your_host_name'; 
$username = 'your_db_username';
$password = 'your_db_password';
$dbname = 'your_db_name';
Ensure your server environment has write permissions for the uploads/ directory (for cover images and PDFs).7. Known Issues(Optional) List any major bugs or limitations here.Developed by: [Your Name]
