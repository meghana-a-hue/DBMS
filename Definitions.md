\# DBMS Important Definitions



\## 1. Primary Key



\- Definition: A primary key is a column (or a set of columns) in a table that uniquely identifies each row.  



\- Rules:

&nbsp; - Must contain unique values.

&nbsp; - Cannot have NULL values.



\- Example:



&nbsp; ```sql

&nbsp; CREATE TABLE Students ( RollNo INT PRIMARY KEY,

&nbsp;                         Name VARCHAR(50),

&nbsp;                         Age INT );



Here, RollNo is the primary key.





\## 2. Foreign Key



* Definition: A foreign key is a column in one table that refers to the primary key of another table. It maintains referential integrity.



* Example:



```sql

CREATE TABLE Orders ( OrderID INT PRIMARY KEY,

&nbsp;                     RollNo INT,

&nbsp;                     FOREIGN KEY (RollNo) REFERENCES Students(RollNo));



Here, RollNo in Orders is a foreign key referencing Students.





\## 3. Candidate Key



* Definition: All columns that can qualify as a primary key are called candidate keys. From these, one is chosen as the primary key.



* Example:



In a table Students(RollNo, Email, Phone), all three could uniquely identify a student. So, RollNo, Email, Phone are candidate keys.





\## 4. Super Key



* Definition: A set of one or more columns that can uniquely identify a row in a table.



* Note: Every primary key is a super key, but not all super keys are primary keys.



* Example:



RollNo, (RollNo, Name) both can act as super keys in Students.





\## 5. Composite Key



* Definition: A primary key made up of two or more columns.



* Example:



```sql

CREATE TABLE ExamResults ( StudentID INT,

&nbsp;                          SubjectCode VARCHAR(10),

&nbsp;                          Marks INT,

&nbsp;                          PRIMARY KEY (StudentID, SubjectCode));



Here, StudentID + SubjectCode together act as the composite key.





\## 6. Unique Key



* Definition: Similar to primary key but allows one NULL value and ensures all values are unique.



* Example:



```sql

CREATE TABLE Employees ( EmpID INT PRIMARY KEY, Email VARCHAR(100) UNIQUE );



Here, Email must be unique but can be NULL.





\## 7. ACID Properties



ACID ensures reliable transactions in a DBMS:



* Atomicity → All operations of a transaction are either fully done or not done at all.



* Consistency → Database moves from one valid state to another valid state.



* Isolation → Transactions are executed independently.



* Durability → Once a transaction is committed, it remains saved even in case of failure.





\## 8. Normalization



* Definition: Process of organizing data to reduce redundancy and improve data integrity.



* Normal Forms:



1\. 1NF → No repeating groups, atomic values.





2\. 2NF → No partial dependency (applies only to composite keys).





3\. 3NF → No transitive dependency.





4\. BCNF → Stronger version of 3NF.







* Example: Splitting Students(Name, Course1, Course2) into separate Students and Courses tables.





\## 9. Constraints



* Definition: Rules applied to table columns to enforce data integrity.



* Types:



NOT NULL → Ensures column cannot store NULL.



UNIQUE → Ensures all values are different.



PRIMARY KEY → Unique + Not Null.



FOREIGN KEY → Refers to another table’s primary key.



CHECK → Ensures condition is met.



DEFAULT → Sets default value.





* Example:



```sql

CREATE TABLE Employee ( EmpID INT PRIMARY KEY,

&nbsp;                       Salary INT CHECK (Salary > 0),

&nbsp;                       City VARCHAR(50) DEFAULT 'Mumbai' );





\## 10. Transactions



* Definition: A transaction is a set of operations that perform a single logical unit of work.



* Properties: Follows ACID rules.



* Example:



```sql

BEGIN TRANSACTION;

UPDATE Accounts SET Balance = Balance - 1000 WHERE AccNo = 101;

UPDATE Accounts SET Balance = Balance + 1000 WHERE AccNo = 102;

COMMIT;

