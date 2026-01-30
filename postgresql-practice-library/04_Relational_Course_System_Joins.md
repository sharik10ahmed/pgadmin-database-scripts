# Project: Relational Course System (SQL Joins)

## 📝 Description
This project simulates a real-world relational database. It splits data into two tables: `Students` and `Courses`, linked by a **Foreign Key**. It demonstrates how to combine this data using various **SQL JOIN** techniques.

## 💻 SQL Script

```sql
-- 1. Create Parent Table (Students)
create table students(
    student_id int primary key,
    student_name varchar(50),
    city varchar(50)
);

insert into students (student_id,student_name,city) values
    (1,'Sam','Delhi'),
    (2,'Colt','Banglore'),
    (3,'Rose','Hyderabad'),
    (4,'Ben','Varanasi');

-- 2. Create Child Table (Courses) with Foreign Key
create table courses(
    course_id int primary key,
    student_id int,
    course_name varchar(50),
    foreign key (student_id) references students(student_id)
);

insert into courses(course_id,student_id,course_name) values
    (101,'1','Django'),
    (102,'1','Python'),
    (103,'2','Data Science'),
    (104,'2','Web Development');

-- 3. INNER JOIN (Matches in both tables)
SELECT 
    students.student_id, 
    students.student_name, 
    students.city, 
    courses.course_name 
FROM students
INNER JOIN courses ON students.student_id = courses.student_id;

-- 4. LEFT JOIN (All students, even if no course)
SELECT 
    students.student_id, 
    students.student_name, 
    students.city, 
    courses.course_name 
FROM students
LEFT JOIN courses ON students.student_id = courses.student_id;

-- 5. RIGHT JOIN (All courses, even if no student)
SELECT 
    students.student_id, 
    students.student_name, 
    students.city, 
    courses.course_name 
FROM students
RIGHT JOIN courses ON students.student_id = courses.student_id;

-- 6. FULL OUTER JOIN (Everything from both)
SELECT 
    students.student_id, 
    students.student_name, 
    students.city, 
    courses.course_name 
FROM students
FULL OUTER JOIN courses ON students.student_id = courses.student_id;