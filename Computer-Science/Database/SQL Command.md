## Part A: Basic Queries

1. Display all records from Student table.

```sql
SELECT * FROM Student;
```

2. Display name and age of students.
 
```sql
SELECT name, age FROM Student;
```

3. Display students whose age is greater than 18.

```sql
SELECT * FROM Student WHERE age > 18;
```

4. Display students from Delhi.

```sql
SELECT * FROM Student WHERE city = 'Delhi';
```

5. Display students sorted by name.

```sql
SELECT * FROM Student ORDER BY name ASC;
```

6. Count total students.

```sql
SELECT COUNT(*) FROM Student;
```

7. Find maximum age.

```sql
SELECT MAX(age) FROM Student;
```

8. Show distinct cities.

```sql
SELECT DISTINCT city FROM Student;
```

9. Students whose name starts with 'A'.

```sql
SELECT * FROM Student WHERE name LIKE 'A%';
```

---
## Part B: INSERT, UPDATE, DELETE

1. Insert a new student.

```sql
INSERT INTO Student (roll_no, name, age, city) VALUES (101, 'Rahul', 20, 'Delhi');
```

**OR**

```sql
insert into student
values(&roll_no, '&name', &marks, '&result')
Enter value of roll_no: 101
Enter value of name: Rakesh Kumar
Enter value of marks: 400
Enter value of result: Pass
```

2. Update city based on `roll_no`.

```sql
UPDATE Student SET city = 'Mumbai' WHERE roll_no = 101;
```

3. Delete student based on `roll_no`.

```sql
DELETE FROM Student WHERE roll_no = 105;
```

---
### Part C: Table Creation

1. Create Student Table

```sql
CREATE TABLE student(
roll_no number(5) primary key,
name varchar2(30) not null,
marks number(4) deafult 0,
result varchar2(8) check (result in ('Pass', 'Fail', 'Reappear', 'RA'))
);
```

```sql
CREATE TABLE Employee (
    emp_id INT PRIMARY KEY,
    emp_name VARCHAR(50),
    salary DECIMAL(10,2),
    department VARCHAR(50)
);
```

2. Add email column

```sql
ALTER TABLE Employee ADD email VARCHAR(100);
```

3. Drop Employee table

```sql
DROP TABLE Employee;
```

4. Show table structure

```sql
desc student
```
==This Command will Show your table structure==

---
### Part D: Aggregate & Group By

1. Average salary

```sql
SELECT AVG(salary) FROM Employee;
```

2. Total salary department-wise

```sql
SELECT department, SUM(salary) 
FROM Employee
GROUP BY department;
```

3. Departments having more than 3 employees

```sql
SELECT department, COUNT(*)
FROM Employee
GROUP BY department
HAVING COUNT(*) > 3;
```

---
### Part E: Joins

Assume: Student`(student_id, name, course_id)` Course`(course_id, course_name)`

1. Student names with course names

```sql
SELECT Student.name, Course.course_name
FROM Student
INNER JOIN Course
ON Student.course_id = Course.course_id;
```

2. All students even if not enrolled (LEFT JOIN)

```sql
SELECT Student.name, Course.course_name
FROM Student
LEFT JOIN Course
ON Student.course_id = Course.course_id
```
