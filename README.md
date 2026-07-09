# Library Management System

This respository contains a virtual Library Management System designed by me as a Self Project using majorly the concepts of OOPS(Object Oriented Programming System).

Welcome to the Library Management System (LMS), a comprehensive C++ program built using OOP concepts and designed to manage books, users, and borrowing activities in a library. This system is developed with simplicity and functionality in mind, making it easy for librarians, students, and faculty members to interact with the library's resources.

The program features a user-friendly menu-driven interface with username-password login system for secure access and with clear instructions for each action. Tables are used to display books, users, and borrowing history for better readability.

## General Features

- **User Roles & Authentication**
  - Students (3-book limit, ₹10/day fines)
  - Faculty (5-book limit, 60-day grace period)
  - Librarians (full admin privileges)

- **Book Management**
  - Add/remove/edit books
  - Track availability (Available/Borrowed/Reserved)
  - Search and display in formatted tables

- **Borrowing System**
  - Automatic due date calculation
  - Overdue tracking with real-time fine updates
  - Borrowing history per user

- **Data Persistence**
  - CSV storage for books/users
  - File locking to prevent corruption
  - Loads previous state on startup

- **Error handling**
  - Rejects invalid ISBNs, passwords, and incorrect data types
  - Defensive programming for all user inputs (e.g., non-integer values in numeric fields)
  - Checks for file locks before write operations


## How to Run the Program

### Prerequisites
- A C++ compiler (e.g., GCC, Clang, or MSVC) supporting C++17. 
- A terminal or command prompt.

### Steps to Run
First clone the repository -
```
git clone https://github.com/ARYAMANN7279/Library-Management-System
cd Library-Management-System
```
Now compile with g++ -
```
g++ -std=c++17 main.cpp -o library
```
Next run the executable -
```
library
```
### Note
* DO NOT open the CSV files before or during the execution of the program, as it might lock the CSV files and not allow the program to write data in it. If the program can't write data on them, it will display an error message - saying CSV file is locked.
* You can freely view the CSV files AFTER running the program, then close the CSV file, then run the program again, and so on. Please use Notepad to view the CSV files. If you use Excel, first turn off the default scientific notation to view the ISBN numbers properly.
* Please run the terminal in FULL SCREEN MODE to view the tables properly. If the width of a row of a table exceeds a line, please REDUCE THE FONT of the terminal to view the table in its proper layout.
* Format of books.csv -
  
  | Genre | Title | Author | Publisher | Year | ISBN | Status |
  | ------| ----- | ------ | --------- | ---- | ---- | ------ |
  
* Format of users.csv -

  | User Id | Username | Password | Role (Student/Faculty/Librarian) | Name | Age | Gender | Borrowing history | Fine |
  | ------- | -------- | -------- | -------------------------------- | ---- | --- | ------ | ----------------- | ---- |
  
* Borrowing history format - Each book's data is separated by ';'. For a single book, the format is -

  | ISBN | Title | Borrowing Date | Return Date | Due Date | Status | Fine |
  | ---- | ----- | -------------- | ----------- | -------- | ------ | ---- |
