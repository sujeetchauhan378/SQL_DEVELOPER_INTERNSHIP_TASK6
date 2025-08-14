# SQL_DEVELOPER_INTERNSHIP_TASK6

## 📌 Task Title
**Subqueries and Nested Queries**

---

## 🎯 Objective
- Practice using **scalar** and **correlated** subqueries.
- Use subqueries inside **SELECT**, **WHERE**, and **FROM** clauses.
- Work with `IN`, `EXISTS`, and `=` operators.

---

## 🛠 Tools Used
- **DB Browser for SQLite** / **MySQL Workbench**

---

## 📂 Deliverables
- SQL queries demonstrating:
  - Scalar subqueries
  - Correlated subqueries
  - Subqueries in `SELECT`, `WHERE`, and `FROM`
  - Use of `IN`, `EXISTS`, `=`
  - Derived tables

---

## 📊 Sample Database Setup

```sql
-- Drop existing tables if any
DROP TABLE IF EXISTS Employees;
DROP TABLE IF EXISTS Departments;
DROP TABLE IF EXISTS Orders;
DROP TABLE IF EXISTS Customers;

-- Create Departments
CREATE TABLE Departments (
    DeptID INT PRIMARY KEY,
    DeptName VARCHAR(50)
);

-- Create Employees
CREATE TABLE Employees (
    EmpID INT PRIMARY KEY,
    EmpName VARCHAR(50),
    DeptID INT,
    Salary DECIMAL(10,2),
    FOREIGN KEY (DeptID) REFERENCES Departments(DeptID)
);

-- Create Customers
CREATE TABLE Customers (
    CustID INT PRIMARY KEY,
    CustName VARCHAR(50)
);

-- Create Orders
CREATE TABLE Orders (
    OrderID INT PRIMARY KEY,
    CustID INT,
    Amount DECIMAL(10,2),
    FOREIGN KEY (CustID) REFERENCES Customers(CustID)
);

-- Insert sample data
INSERT INTO Departments VALUES
(1, 'HR'), (2, 'IT'), (3, 'Sales');

INSERT INTO Employees VALUES
(101, 'John', 1, 50000),
(102, 'Emma', 1, 60000),
(103, 'Ava', 2, 75000),
(104, 'Liam', 2, 90000),
(105, 'Noah', 3, 45000);

INSERT INTO Customers VALUES
(1, 'Alice'), (2, 'Bob'), (3, 'Charlie');

INSERT INTO Orders VALUES
(1, 1, 2000),
(2, 1, 1500),
(3, 2, 3000),
(4, 3, 500);
