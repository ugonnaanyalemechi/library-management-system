# Library Management System

A console-based application designed to streamline library operations. This project demonstrates proficiency in **Modern C++ (C++20)**, **Object-Oriented Programming (OOP)**, and **Database Management (PostgreSQL)**.

## Tech Stack
* **Language:** C++20
* **Database:** PostgreSQL
* **Database Connector:** libpqxx
* **Build System:** CMake
* **Security:** SHA-256 Hashing (Authentication)

## Key Features

This system implements role-based access control with distinct functionalities for general members and library administrators.

### Security & Accounts
* **Secure Authentication:** User passwords are hashed using SHA-256 before storage.
* **Input Validation:** Robust handling of user inputs to prevent SQL errors and logical faults.
* **Registration:** Dynamic sign-up flow checking for duplicate emails and valid Personally Identifiable Information.

### Member Features
* **Rich Search:** Users can search for books by Title, Author, or Genre using optimized database text queries.
* **Account Management:** Self-service capabilities to edit personal details and credentials.

### Administrator Features
* **Inventory Control:** Full CRUD (Create, Read, Update, Delete) capabilities for the book catalog.
* **Staff Management:** Ability to promote existing members to staff status.
* **User Oversight:** Search and manage library member profiles.

## System Architecture

The project is structured around a modular **Object-Oriented Design**, ensuring separation of concerns and maintainability.

### Core Modules
1.  **MenuManager:** Acts as the presentation layer, handling the CLI loop and routing user input to the appropriate logic controllers.
2.  **AccountManager:** Handles the business logic for user session management, registration, and profile editing.
3.  **BookManager:** Manages administrative operations for the book catalog, ensuring data integrity during additions or deletions.
4.  **BookSearch:** Specialized module utilizing PostgreSQL `_tsvector` for efficient, full-text searching of the library catalog.

### Data Persistence
* **PostgreSQL Integration:** The application connects directly to a remote Postgres instance.
* **Prepared Statements:** All database interactions utilize prepared statements to prevent SQL injection and improve query performance.

## Getting Started

### Prerequisites
* C++ Compiler (supporting C++20)
* CMake (Version 3.8+)
* PostgreSQL Database

### Build Instructions

```bash
# Clone the repository
git clone <repository-url>

# Create build directory
mkdir build && cd build

# Configure with CMake
cmake ..

# Build the executable
cmake --build .

```
### Database Setup
Ensure connInfo.txt is present in the root directory containing your PostgreSQL connection string, and execute schema.sql to initialize tables.
