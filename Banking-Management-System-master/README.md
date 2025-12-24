# 🏦 Banking Management System

A robust, console-based Java application designed to handle core banking operations with a focus on transactional integrity and secure data management. This project demonstrates the integration of **Java Database Connectivity (JDBC)** with a **MySQL** backend to simulate real-world financial workflows.

## 🌟 Key Technical Features

* **Transaction Management (ACID Compliance):** Implements manual commit and rollback logic in the `AccountManager` class to ensure that money transfers are atomic—either both the debit and credit succeed, or neither does.
* **Secure User Authentication:** Features a registration and login system that validates unique email addresses and protects user sessions.
* **Automated Account Generation:** Uses logic to generate unique 8-digit account numbers (starting at 10000100) based on the last entry in the database.
* **Data Validation:** Includes security pin verification for every sensitive action, including debits, credits, and balance inquiries, to prevent unauthorized access.

## 🛠 Tech Stack

* **Language:** Java (JDK 20)
* **Database:** MySQL
* **API:** JDBC (Java Database Connectivity)
* **Build Tool:** IntelliJ IDEA Module Structure

## 📂 Project Architecture

### Database Schema
The system utilizes a relational database design with two primary tables: `user` for authentication and `accounts` for financial records.



![Database Schema](Database%20Schema.png)

### Core Modules
* **`BankingApp.java`**: The main entry point handling the application loop, menu navigation, and database connection initialization.
* **`AccountManager.java`**: Contains the critical business logic for debits, credits, and inter-bank transfers.
* **`Accounts.java`**: Manages account opening, existence checks, and account number generation.
* **`User.java`**: Handles user registration and login validation against the MySQL database.

## 🚀 Getting Started

1.  **Clone the Repository**:
    ```bash
    git clone [https://github.com/pranjli-s/bankingsystem.git](https://github.com/pranjli-s/bankingsystem.git)
    ```
2.  **Configure the Database**:
    * Create a database named `banking_system` in MySQL.
    * Execute the schema found in the `Database Schema.png` visual.
    * Update the `url`, `username`, and `password` variables in `BankingApp.java` to match your local MySQL credentials.
3.  **Compile and Run**:
    * Ensure the `mysql-connector-j-8.1.0.jar` is added to your project's library path.
    * Run `BankingApp.java`.

## 📸 Demo Highlights
* **Registration:** Create a new user profile securely with duplicate email detection.
* **Transactions:** Perform real-time balance updates (Credit/Debit) with instant feedback.
* **Security:** Unauthorized transfers and balance checks are blocked if the security pin is incorrect.