# 🏦 Banking Management System

A robust, console-based Java application designed to handle core banking operations with a focus on transactional integrity and secure data management. This project demonstrates the integration of **Java Database Connectivity (JDBC)** with a **MySQL** backend to simulate real-world financial workflows.

## 🌟 Key Technical Features

* **Transaction Management (ACID Compliance):** Implements manual commit and rollback logic in the `AccountManager` class. This ensures that money transfers are atomic—either both the debit and credit succeed, or the entire transaction is rolled back to prevent data inconsistency.
* **Secure User Authentication:** Features a registration and login system that validates unique email addresses and protects user sessions via password-protected access.
* **Automated Account Generation:** Uses logic to fetch the last assigned account number from the database and generate a unique 8-digit successor (starting at 10000100).
* **Multi-Layer Security:** Includes security pin verification for all sensitive operations, including debits, credits, and balance inquiries.

## 🛠 Tech Stack

* **Language:** Java (JDK 20)
* **Database:** MySQL 8.0
* **API:** JDBC (Java Database Connectivity)
* **Driver:** MySQL Connector/J 8.1.0

## 📂 Project Architecture

### Data Model
The system utilizes a relational database design consisting of two primary tables:
* **User Table:** Manages authentication data including Full Name, Email (Primary Key), and Password.
* **Accounts Table:** Manages financial data including Account Number (Primary Key), Balance (Decimal), and a 4-digit Security Pin.

### Core Modules
* **`BankingApp.java`**: The main controller that manages the application lifecycle, user menus, and the central database connection.
* **`AccountManager.java`**: Handles the critical business logic for credit, debit, and inter-bank money transfers using SQL PreparedStatements.
* **`Accounts.java`**: Responsible for account lifecycle management, including account opening and existence verification.
* **`User.java`**: Manages the user registration pipeline and login authentication logic.

## 🚀 Getting Started

1.  **Clone the Repository**:
    ```bash
    git clone [https://github.com/pranjli-s/bankingsystem.git](https://github.com/pranjli-s/bankingsystem.git)
    ```
2.  **Database Setup**:
    * Create a MySQL database named `banking_system`.
    * Create the `user` and `accounts` tables as defined in the source code models.
    * Update the `url`, `username`, and `password` constants in `BankingApp.java` to match your local environment.
3.  **Dependencies**:
    * Ensure the `mysql-connector-j-8.1.0.jar` is included in your project's build path or library folder.
4.  **Run**:
    * Compile and run `BankingApp.java` to start the console interface.

## 💡 Functional Highlights
* **Account Opening:** Requires an initial deposit and the setting of a secret 4-digit transaction pin.
* **Atomic Transfers:** Prevents "ghost money" by ensuring a sender is debited only if the receiver is successfully credited.
* **Validation:** Prevents over-drafting by checking balances before authorizing any debit request.