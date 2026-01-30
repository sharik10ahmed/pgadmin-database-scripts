# PgAdmin4 Employee Manager

## 📝 Description
This project contains essential SQL scripts for managing an employee database using **PostgreSQL** and **pgAdmin 4**. It demonstrates the fundamental operations of a database lifecycle, including creating schemas, populating data, managing records, and cleaning up resources.

This repository serves as a practical example for handling `Employee` records with fields for ID, Name, Age, and Designation.

## 🚀 Features
The SQL script covers the following CRUD (Create, Read, Update, Delete) and DDL (Data Definition Language) operations:
* **Create:** Establishing the database structure with primary keys and auto-incrementing serials.
* **Insert:** Populating the table with sample employee data (Developers, Managers, Associates).
* **Select:** Retrieving and viewing all stored records.
* **Delete:** Removing specific records based on their unique ID.
* **Drop:** Safely removing the table structure from the database.

## 🛠️ Technology Stack
* **Database:** PostgreSQL
* **Management Tool:** pgAdmin 4
* **Language:** SQL

## 💻 Usage Instructions
1. Open **pgAdmin 4** and connect to your database server.
2. Open the **Query Tool** for your specific database.
3. Copy and paste the SQL commands below to run the operations.

### SQL Script
```sql
-- 1. Create the Employee Table
CREATE TABLE Employee(
    id SERIAL PRIMARY KEY,
    name VARCHAR(200),
    age INT,
    designation VARCHAR(200)
);

-- 2. View the Empty Table
SELECT * FROM Employee;

-- 3. Insert Sample Data
INSERT INTO Employee(name, age, designation)
VALUES
    ('Sam', 21, 'Dev'),
    ('Colines', 22, 'Senior Dev'),
    ('Samuel', 24, 'Manager'),
    ('Rose', 25, 'General Manager'),
    ('Easton', 28, 'Financial Associate');

-- 4. Delete Specific Records
DELETE FROM Employee WHERE id = 2; -- Removes Colines
DELETE FROM Employee WHERE id = 4; -- Removes Rose

-- 5. Drop the Table (Cleanup)
DROP TABLE Employee;