\# SQL Data Types



SQL Data Types define the kind of data that can be stored in a table column. Choosing the correct data type ensures data integrity, efficient storage, and accurate queries.





\## 1. Numeric Data Types



Used to store numbers (integer or decimal).



* \*INT / INTEGER\* → Whole numbers  

&nbsp; 

* Example: 100, -45, 0  

&nbsp; 

```sql

&nbsp; CREATE TABLE Students ( RollNo INT PRIMARY KEY, Age INT );



SMALLINT → Smaller range of integers (saves space).

Example: 32767, -32768



BIGINT → Very large integer values.

Example: 9223372036854775807



DECIMAL(p,s) / NUMERIC(p,s) → Fixed-point numbers with precision (p = total digits, s = digits after decimal).

Example: DECIMAL(6,2) → 1234.56



FLOAT / REAL / DOUBLE → Approximate values (for scientific calculations).

Example: 3.14159





\## 2. String Data Types



Used to store text, characters, and words.



CHAR(n) → Fixed-length string (n characters).

Example: CHAR(5) → 'Amit ' (always 5 chars, padded with spaces).



VARCHAR(n) → Variable-length string (up to n characters).

Example: VARCHAR(50) → "Meghana" (stores only needed length).



TEXT → Very large text (paragraphs, articles).



```sql

CREATE TABLE Books ( Title VARCHAR(100), Author VARCHAR(50), Description TEXT );





\## 3. Date and Time Data Types



Used to handle date, time, and timestamp values.



DATE → Stores only date in format YYYY-MM-DD

Example: 2025-08-16



TIME → Stores only time in format HH:MM:SS

Example: 15:45:30



DATETIME / TIMESTAMP → Stores both date and time.

Example: 2025-08-16 15:45:30



YEAR → Stores year in 2 or 4 digits.

Example: 2025



```sql

CREATE TABLE Events ( EventName VARCHAR(100),

&nbsp;                     EventDate DATE,

&nbsp;                     EventTime TIME );





\## 4. Boolean Data Type



BOOLEAN / BOOL → Stores TRUE or FALSE (internally as 1 or 0).

Example: isActive BOOLEAN





```sql

CREATE TABLE Users ( UserID INT,

&nbsp;                    Username VARCHAR(50),

&nbsp;                    IsActive BOOLEAN );





\## 5. Binary Data Types



Used to store images, files, or multimedia content.



BLOB (Binary Large Object) → Stores large binary data like images, videos.



BINARY(n) → Fixed-length binary data.



VARBINARY(n) → Variable-length binary data.





* Example:



CREATE TABLE Files ( FileID INT,

&nbsp;                    FileName VARCHAR(100),

&nbsp;                    FileData BLOB );





\## 6. Special Data Types (Vendor Specific)



ENUM → A list of predefined values.

Example:



```sql

CREATE TABLE Orders ( Status ENUM('Pending', 'Shipped', 'Delivered', 'Cancelled'));



SET → A collection of multiple predefined values.

Example:



```sql

CREATE TABLE StudentSkills ( Skills SET('Java','Python','SQL','C++'));





\## Summary



Numeric Types → INT, BIGINT, DECIMAL, FLOAT



String Types → CHAR, VARCHAR, TEXT



Date/Time Types → DATE, TIME, DATETIME, TIMESTAMP



Boolean → TRUE / FALSE



Binary → BLOB, BINARY, VARBINARY



Special → ENUM, SET

