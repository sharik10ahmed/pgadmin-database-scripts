# Project: Advanced Employee Operations

## 📝 Description
This project focuses on **Schema Management** (changing the structure of the database). It demonstrates how to add/remove columns, rename tables, and filter data by city.

## 💻 SQL Script

```sql
-- 1. Create Initial Table with City
create table Employee(
    id serial primary key,
    name varchar(200),
    age int,
    designation varchar(200),
    city varchar(200)
);

select * from Employee;

-- 2. Bulk Insert
insert into employee (name, age, designation, city)
values 
    ('Sam', 21, 'Senior Dev', 'Bangalore'),
    ('Aria', 24, 'Data Analyst', 'Mumbai'),
    ('Ethan', 30, 'Product Manager', 'Delhi'),
    ('Zara', 27, 'UI/UX Designer', 'Pune'),
    ('Liam', 22, 'Junior Dev', 'Hyderabad'),
    ('Noah', 35, 'Tech Lead', 'Chennai'),
    ('Mia', 26, 'QA Engineer', 'Kolkata'),
    ('Lucas', 29, 'DevOps Engineer', 'Ahmedabad'),
    ('Sana', 32, 'Project Manager', 'Gurgaon');

-- 3. Modifying the Table Structure (ALTER)
Alter table employee
add phone_number varchar(200);

-- 4. Cleaning Data
alter table employee
drop phone_number;

truncate table employee; -- Removes all data but keeps table

-- 5. Updating and Deleting
update employee
set name ='Rose'
where id=5;

delete from employee where id=2;
delete from employee where id=4;

-- 6. Renaming Operations
ALTER TABLE staff RENAME TO Employee;
ALTER TABLE employee RENAME COLUMN job_role TO designation;

-- 7. Advanced Queries
SELECT name, designation 
FROM employee 
WHERE city = 'Mumbai';

SELECT * FROM employee ORDER BY age DESC;