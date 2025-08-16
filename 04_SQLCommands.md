\# SQL Commands



SQL (Structured Query Language) is used to interact with databases.  

It allows us to create, insert, update, delete, and retrieve data.



---



\## 1. CREATE (Table name - Students)

Used to create a new table in the database.  



```sql

CREATE TABLE Students ( RollNo INT PRIMARY KEY,

&nbsp;                       Name VARCHAR(50),

&nbsp;                       Age INT,

&nbsp;                       Course VARCHAR(50));



\## 2. INSERT

Used to add new records into a table.  



```sql

INSERT INTO Students (RollNo, Name, Age, Course) VALUES (1, 'Meghana', 20, 'BCA');





\## 3. SELECT

Used to retrieve data from a table.



```sql

--Select all columns from Students table



SELECT \* FROM Students;





\## 4. UPDATE



Used to modify existing records.



```sql

UPDATE Students SET Course = 'MCA' WHERE RollNo = 1;



UPDATE Students SET Age = 22 WHERE Name = 'Aadesh';





\## 5. DELETE



Used to remove records from a table.



```sql

DELETE FROM Students WHERE RollNo = 2;



DELETE FROM Students WHERE Age < 18;





\## 6. JOIN



Used to combine data from two or more tables.



-- Example with Students and Courses table



```sql

SELECT Students.Name, Courses.CourseName FROM Students INNER JOIN Courses ON Students.Course = Courses.CourseID;



\## Summary



-- CREATE → Make a table



-- INSERT → Add data



-- SELECT → Retrieve data



-- UPDATE → Modify data



-- DELETE → Remove data



-- JOIN → Combine tables



