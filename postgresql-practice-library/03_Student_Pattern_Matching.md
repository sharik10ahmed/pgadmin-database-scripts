# Project: Student Database & Filtering

## 📝 Description
This script handles a Student database and focuses on **Data Searching**. It uses logical operators (`AND`, `OR`, `IN`) and wildcard pattern matching (`LIKE`) to find students based on names or courses.

## 💻 SQL Script

```sql
create table student(
    id serial primary key,
    name varchar(200),
    age int,
    course varchar(200)
);

insert into student(name,age,course)
values
    ('Sam',18,'Python'),
    ('Elena', 20, 'Data Science'),
    ('Marcus', 19, 'Java'),
    ('Priya', 21, 'Machine Learning'),
    ('Julian', 18, 'Web Development'),
    ('Chloe', 22, 'Cybersecurity');

-- 1. Corrections (Updates)
update student set name = 'Amit Kumar' where id = 2;
update student set name = 'Rahul Sharma' where id = 5;
update student set name = 'Aman Sonkar' where id = 6;
update student set course = 'Data Science' where id = 5;

-- 2. Logical Queries
select * from student
where  course = 'Data Science' and course = 'Data Science';

select * from student
where id = 2 or id = 5;

select * from student
where id in (1, 3, 5);

-- 3. Schema Update
ALTER TABLE student ADD city VARCHAR(50);
UPDATE student SET city = 'Delhi' WHERE id = 5;

-- 4. Pattern Matching (LIKE)
select * from student where name like 'A%'; -- Starts with A
select * from student where name like '%a'; -- Ends with a
select * from student where course like '%enc%'; -- Contains 'enc'