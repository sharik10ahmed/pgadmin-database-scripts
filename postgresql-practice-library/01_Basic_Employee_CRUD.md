# Project: Basic Employee Record System

## 📝 Description
This script demonstrates the foundational operations of SQL (CRUD). It creates a simple employee table, populates it with staff data, and performs specific deletions based on ID.

## 💻 SQL Script

```sql
-- 1. Create the Table
create table Employee(
    id serial primary key,
    name varchar(200),
    age int,
    designation varchar(200)
);

-- 2. Check Data
select * from employee;

-- 3. Insert Records
insert into employee(name,age,designation)
values
    ('Sam',21,'Dev'),
    ('Colines',22,'Senior Dev'),
    ('Samuel',24,'Manger'),
    ('Rose',25,'General Manager'),
    ('Easton',28,'Financial Associate');

-- 4. Delete Specific Records
delete from employee where id=2;
delete from employee where id=4;

-- 5. Cleanup
drop table employee;