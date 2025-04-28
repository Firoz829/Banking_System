# HDFC Banking System - Java Console Application

**HDFC Banking System** is a console-based banking application developed using **Java**, **JDBC**, and **MySQL**.  
It offers a basic banking experience through a command-line interface with secure login, account management, and transaction features.

---

## Features 🚀
- **User Registration** — Register with full name, email, and password.
- **Secure Login** — Login with email and password authentication.
- **Bank Account Management:**
  - Open a new account with initial deposit and security PIN.
  - Deposit and withdraw money securely.
  - Transfer money to another user using account number.
  - Check account balance after PIN verification.
- **Security:** PIN is required for sensitive operations (transfer, check balance).
- **Menu Driven:** Easy-to-use and intuitive console menu system.

---

## Technologies Used 🛠️
- Java
- JDBC (Java Database Connectivity)
- MySQL

---

## Console Preview 📜
```text
*** WELCOME TO HDFC BANKING SYSTEM ***

1. Register
2. Login
3. Exit
Enter your choice: 1
Full Name: Firoz Shaikh
Email: firoz@gmail.com
Password: Firoz123@

Registration Successful!

*** WELCOME TO HDFC BANKING SYSTEM ***

1. Register
2. Login
3. Exit
Enter your choice: 2
Email: firoz@gmail.com
Password: Firoz123@

User Logged In!

1. Open a new Bank Account
2. Exit
Enter your choice: 1
...
```

---

## Database Schema 📂

You need to create the following tables in MySQL:

### 1. `users` Table
| Column Name | Data Type  | Description               |
|-------------|------------|----------------------------|
| id          | INT        | Primary Key, Auto-Increment |
| fullname    | VARCHAR(100) | Full name of the user       |
| email       | VARCHAR(100) | User email (must be unique) |
| password    | VARCHAR(100) | User password (hashed or plain) |

---

### 2. `accounts` Table
| Column Name   | Data Type    | Description                     |
|---------------|--------------|---------------------------------|
| account_no    | INT          | Primary Key, Auto-Increment     |
| user_id       | INT          | Foreign Key (references `users`)|
| fullname      | VARCHAR(100) | Account holder’s name           |
| balance       | DOUBLE       | Current account balance         |
| security_pin  | INT          | 4-digit PIN for security        |

---

## Setup Instructions ⚙️

1. **Clone the repository**  
   ```bash
   git clone https://github.com/your-username/your-repo-name.git
   ```

2. **Create the MySQL database and tables**  
   Example:
   ```sql
   CREATE DATABASE banking_system;

   USE banking_system;

   CREATE TABLE users (
       id INT AUTO_INCREMENT PRIMARY KEY,
       fullname VARCHAR(100),
       email VARCHAR(100) UNIQUE,
       password VARCHAR(100)
   );

   CREATE TABLE accounts (
       account_no INT AUTO_INCREMENT PRIMARY KEY,
       user_id INT,
       fullname VARCHAR(100),
       balance DOUBLE,
       security_pin INT,
       FOREIGN KEY (user_id) REFERENCES users(id)
   );
   ```

3. **Update the database credentials**  
   In your Java project, update your JDBC connection file:
   ```java
   String url = "jdbc:mysql://localhost:3306/banking_system";
   String user = "your_mysql_username";
   String password = "your_mysql_password";
   ```

4. **Compile and Run the Java Project**
   ```bash
   javac YourMainFile.java
   java YourMainFile
   ```

---

## Notes 📌
- Make sure MySQL server is running locally.
- Use proper exception handling in JDBC connections.
- Passwords should ideally be encrypted for real-world applications.

---

## Author 👤
- **Firoz Shaikh**



