\# SQL Clauses and Functions



SQL provides different clauses and functions to filter, search, and perform calculations on data.





\## 1. WHERE Clause

Used to filter records based on a condition.



```sql

SELECT \* FROM Students WHERE Age > 18;

SELECT \* FROM Students WHERE Course = 'BCA';





\## 2. LIKE Operator



Used for pattern matching in strings.



-- Name starting with 'S'



```sql

SELECT \* FROM Students WHERE Name LIKE 'S%';



-- Name ending with 's'



```sql

SELECT \* FROM Students WHERE Name LIKE '%s';



-- Name containing 'an'



```sql

SELECT \* FROM Students WHERE Name LIKE '%an%';





\## 3. ORDER BY



Used to sort results in ascending (ASC) or descending (DESC) order.



```sql

SELECT \* FROM Students ORDER BY Name ASC;

SELECT \* FROM Students ORDER BY Age DESC;





\## 4. Aggregate Functions



Used to perform calculations on a set of values.



-- Maximum age



```sql

SELECT MAX(Age) FROM Students;



-- Minimum age



```sql

SELECT MIN(Age) FROM Students;



-- Average age



```sql

SELECT AVG(Age) FROM Students;



-- Total number of students



```sql

SELECT COUNT(\*) FROM Students;



-- Sum of all ages



```sql

SELECT SUM(Age) FROM Students;





\## 5. GROUP BY



Used to group rows that have the same values.



```sql

SELECT Course, COUNT(\*) FROM Students GROUP BY Course;





\## 6. HAVING



Used with GROUP BY to filter groups.



```sql

SELECT Course, COUNT(\*) FROM Students GROUP BY Course HAVING COUNT(\*) > 2;





\## Summary



-- WHERE → Filter rows



-- LIKE → Search patterns



-- ORDER BY → Sort results



-- MAX, MIN, AVG, SUM, COUNT → Aggregate functions



-- GROUP BY → Group similar rows



-- HAVING → Filter groups

