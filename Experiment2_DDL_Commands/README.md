Experiment 2: DDL Commands
NAME:MAHASRI D
REG.NO:212224220058

AIM

To study and implement DDL commands and different types of constraints.

THEORY

1. CREATE
Used to create a new relation (table).
Syntax:
```
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
 ...
);
```

2. ALTER
Used to add, modify, drop, or rename fields in an existing relation. (a) ADD
```
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```

3. DROP TABLE
Used to permanently delete the structure and data of a table.
```
DROP TABLE relation_name;
```

4. RENAME
Used to rename an existing database object.
```
RENAME TABLE old_relation_name TO new_relation_name;
```


CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).

1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column. Syntax:
```
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```

2. UNIQUE
Ensures that values in a column are unique. Syntax:
```
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```

3. CHECK
Specifies a condition that each row must satisfy. Syntax:
```
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```

4. PRIMARY KEY
Used to uniquely identify each record in a table. Properties: Must contain unique values. Cannot be null. Should contain minimal fields. Syntax:
```
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```

5. FOREIGN KEY
Used to reference the primary key of another table. Syntax:
```
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```

6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

Question 1

Create a new table named item with the following specifications and constraints:

item_id as TEXT and as primary key.
item_desc as TEXT.
rate as INTEGER.
icom_id as TEXT with a length of 4.
icom_id is a foreign key referencing com_id in the company table.
The foreign key should cascade updates and deletes.
item_desc and rate should not accept NULL.
```
CREATE TABLE item(
item_id TEXT,
item_desc TEXT,
rate INT,
icom_id TEXT CHECK (LENGTH(icom_id)=4),
FOREIGN KEY (icom_id) REFERENCES company (com_id) ON UPDATE CASCADE ON DELETE CASCADE
);
```
Output:
<img width="1233" height="207" alt="image" src="https://github.com/user-attachments/assets/35e2e5b7-3867-4025-bca2-1a21a34c4417" />


Question 2

Insert all books from Out_of_print_books into Books Table attributes are ISBN, Title, Author, Publisher, YearPublished
```
INSERT INTO Books (ISBN, Title, Author, Publisher, YearPublished)
SELECT ISBN, Title, Author, Publisher, YearPublished FROM Out_of_print_books;
```
Output:
<img width="1182" height="126" alt="image" src="https://github.com/user-attachments/assets/3086bf1e-8c16-42b0-b5a3-e62f624146aa" />

Question 3

Write a SQL query to Add a new column Country as text in the Student_details table. Sample table: Student_details
```
ALTER TABLE Student_details ADD Country TEXT;
```
Output:
<img width="1165" height="176" alt="image" src="https://github.com/user-attachments/assets/60a9dfc6-1ab3-4899-939a-9ab85a2a1528" />

Question 4

Create a table named Locations with the following columns:

LocationID as INTEGER
LocationName as TEXT
Address as TEXT
```
CREATE TABLE Locations(
LocationID INTEGER,
LocationName TEXT,
Address TEXT
);
```
Output:
<img width="1749" height="250" alt="image" src="https://github.com/user-attachments/assets/57bda6c8-904a-4d79-b61c-d16a9fd128d7" />



Question 5

Insert a book with ISBN 978-1234567890, Title Data Science Essentials, Author Jane Doe, Publisher TechBooks, and Year 2024 into the Books table.
```
INSERT INTO Books (ISBN,Title,Author,Publisher,Year)
VALUES ('978-1234567890','Data Science Essentials','Jane Doe','TechBooks',2024);
```
Output:
<img width="1752" height="151" alt="image" src="https://github.com/user-attachments/assets/dd49d508-def6-4ad2-9178-48a619fe2e59" />


Question 6

In the Student_details table, insert a student record where some fields are NULL, another record where all fields are filled without any NULL values, and a third record where some fields are filled, and others are left as NULL.
```
INSERT INTO Student_details (RollNo,Name,Gender,Subject,MARKS)
VALUES (205,'Olivia Green','F',NULL,NULL),
(207,'Liam Smith','M','Mathematics',85),
(208,'Sophia Johnson','F','Science',NULL);
```
Output:
<img width="1809" height="234" alt="image" src="https://github.com/user-attachments/assets/4fc262a7-bca7-4329-9219-0311c052ab73" />

Question 7

Create a table named Bonuses with the following constraints:

BonusID as INTEGER should be the primary key.
EmployeeID as INTEGER should be a foreign key referencing Employees(EmployeeID).
BonusAmount as REAL should be greater than 0.
BonusDate as DATE.
Reason as TEXT should not be NULL.
```
CREATE TABLE Bonuses(
BonusID INT PRIMARY KEY,
EmployeeID INT,
BonusAmount REAL,
BonusDate DATE,
Reason TEXT NOT NULL,
FOREIGN KEY (EmployeeID) REFERENCES Employees (EmployeeID),
CHECK (BonusAmount>0)
);
```
Output:
<img width="1830" height="131" alt="image" src="https://github.com/user-attachments/assets/db02a220-e7e2-4cff-ac90-29a69ce519ad" />



Question 8

create a table named jobs including columns job_id, job_title, min_salary and max_salary, and make sure that, the default value for job_title is blank and min_salary is 8000 and max_salary is NULL will be entered automatically at the time of insertion if no value assigned for the specified columns.
```
CREATE TABLE jobs(
job_id INTEGER,
job_title TEXT DEFAULT 'black',
min_salary INT DEFAULT 8000,
max_salary INT DEFAULT NULL
);
```
Output:
<img width="1395" height="148" alt="image" src="https://github.com/user-attachments/assets/d5f04e73-cbe8-4ae4-a04b-3df5721342c9" />


Question 9

Write an SQL Query to add the attributes designation, net_salary, and dob to the Companies table with the following data types:

designation as VARCHAR(50)
net_salary as NUMBER
dob as DATE
```
ALTER TABLE Companies ADD designation varchar(50);
ALTER TABLE Companies ADD net_salary number;
ALTER TABLE Companies ADD dob date;
```
Output:
<img width="1704" height="317" alt="image" src="https://github.com/user-attachments/assets/08f2a537-1e29-4454-a47e-db1064531e2b" />

Question 10

Create a table named Invoices with the following constraints:

InvoiceID as INTEGER should be the primary key.
InvoiceDate as DATE.
Amount as REAL should be greater than 0.
DueDate as DATE should be greater than the InvoiceDate.
OrderID as INTEGER should be a foreign key referencing Orders(OrderID).
```
CREATE TABLE Invoices(
InvoiceID INTEGER PRIMARY KEY,
InvoiceDate DATE,
Amount REAL,
DueDate DATE,
OrderID INTEGER,
FOREIGN KEY (OrderID) REFERENCES Orders (OrderID),
CHECK (LENGTH(Amount)>0),
CHECK (DueDate>InvoiceDate)
);
```
Output:
<img width="1805" height="146" alt="image" src="https://github.com/user-attachments/assets/5559b800-2945-49da-b60d-1f5eb32c4187" />



RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.

Module 1 Grade:
<img width="1012" height="82" alt="image" src="https://github.com/user-attachments/assets/b5116f81-9b0a-40e9-b2ce-cfe60b37888e" />
