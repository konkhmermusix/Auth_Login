==================================================
AUTH_LOGIN - PHP & MySQL Authentication System
==================================================

Project Description
-------------------
AUTH_LOGIN is a simple Authentication System built with:
- PHP (Core PHP)
- MySQL
- Bootstrap

Features:
- User Registration
- User Login / Logout
- Role System (Admin / User)
- Password Hash Security
- Dashboard Page
- Last Login Tracking


==================================================
HOW TO CLONE PROJECT
==================================================

1. Clone from GitHub

   git clone https://github.com/konkhmermusix/Auth_Login.git

2. Move project folder to:

   xampp/htdocs/
   OR
   laragon/www/

3. Start Apache and MySQL


==================================================
DATABASE SETUP
==================================================

1. Open phpMyAdmin:
   http://localhost/phpmyadmin

2. Run the following SQL:

--------------------------------------------------

CREATE DATABASE IF NOT EXISTS auth_login 
CHARACTER SET utf8mb4 
COLLATE utf8mb4_unicode_ci;

USE auth_login;

CREATE TABLE IF NOT EXISTS users (
    id INT(11) AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) NOT NULL UNIQUE,
    email VARCHAR(100) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL,
    role ENUM('admin', 'user') DEFAULT 'user',
    phone VARCHAR(20),
    address TEXT,
    status TINYINT(1) DEFAULT 1,
    last_login TIMESTAMP NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP 
        ON UPDATE CURRENT_TIMESTAMP
) ENGINE=InnoDB;

--------------------------------------------------


==================================================
DATABASE CONFIGURATION
==================================================

Open file:
inc/db.php

<?php

$host = "localhost";
$user = "root";
$pass = "";
$db   = "auth_login";

$conn = new mysqli($host, $user, $pass, $db);

if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}


==================================================
HOW TO RUN PROJECT
==================================================

Open your browser:

http://localhost/Auth_Login/


==================================================
PROJECT STRUCTURE
==================================================

AUTH_LOGIN/
│
├── dashboard/
│   ├── dashboard.php
│   └── inc/
│       ├── header.php
│       └── footer.php
│
├── database/
│   └── ecommerce.txt
│
├── inc/
│   ├── db.php
│   ├── header.php
│   └── footer.php
│
├── static/
│   ├── bootstrap-icons/
│   ├── css/
│   ├── image/
│   └── js/
│
├── index.php
├── login.php
├── register.php
├── logout.php
└── .gitignore


==================================================
SYSTEM REQUIREMENTS
==================================================

- PHP 7.4 or higher
- MySQL
- XAMPP


==================================================
Developed By
==================================================

Leav Sis
LS Tech Cambodia

==================================================
