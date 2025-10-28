Experiment 3: DML Commands

Name:MAHASRI D

Reg.no:212224220058


AIM

To study and implement DML (Data Manipulation Language) commands.

THEORY

1. INSERT INTO
Used to add records into a relation. These are three type of INSERT INTO queries which are as A)Inserting a single record Syntax (Single Row):
```
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
Syntax (Multiple Rows):
```
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
Syntax (Insert from another table):
```
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
2. UPDATE
Used to modify records in a relation. Syntax:
```
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
3. DELETE
Used to delete records from a relation. Syntax (All rows):
```
DELETE FROM table_name;
```
Syntax (Specific condition):
```
DELETE FROM table_name WHERE condition;
```
4. SELECT
Used to retrieve records from a table. Syntax:
```
SELECT column1, column2 FROM table_name WHERE condition;
```
Question 1

Write a SQL statement to update the product_name as 'Grapefruit' whose product_id is 4 in the products table.
```
update products
set product_name='Grapefruit'
where product_id=4;
```
Output:

<img width="522" height="137" alt="image" src="https://github.com/user-attachments/assets/6abb032a-4b7c-426d-9a07-ce5ea0483e11" />



Question 2

Write a SQL query to reduce the reorder level by 30% where cost price is more than 50 and quantity in stock is less than 100 in the products table.
```
update Products
set reorder_lvl=reorder_lvl*0.7
where cost_price>50 and quantity<100;
```
Output:

<img width="768" height="292" alt="image" src="https://github.com/user-attachments/assets/11d60beb-275e-4307-9299-6012e4444285" />


Question 3

Write a SQL query to Delete a Specific Surgery which was made on 28th Feb 2024.
```
delete from Surgeries 
where surgery_date='2024-02-28';
```
Output:

<img width="508" height="293" alt="image" src="https://github.com/user-attachments/assets/5d2f2625-350f-4209-b73e-6609dd904112" />


Question 4

Write a SQL query to Delete customers from 'customer' table where 'GRADE' is not equal to 3.
```
delete from customer
where GRADE!=3;
```
Output:

<img width="172" height="451" alt="image" src="https://github.com/user-attachments/assets/0f651103-f4af-4fa9-857e-ab069c094a88" />


Question 5

Write a query to fetch details of employees whose EmpLname ends with an alphabet ‘A’ and contains five alphabets.
```
select * from EmployeeInfo 
where EmpLname like '%A' and length(EmpLname)=5;
```
Output:

<img width="953" height="173" alt="image" src="https://github.com/user-attachments/assets/134e48bd-db3f-42c1-b2af-a738fe389426" />


Question 6

Write a SQL query to classify base in the Calculations table as 'Provided' if it is not NULL, otherwise 'Not Provided'.
```
select id,base,
case when base is not NULL then 'Provided'
else 'Not Provided'
end as base_status
from Calculations;
```
Output:

<img width="393" height="413" alt="image" src="https://github.com/user-attachments/assets/0acbd19f-0020-4e16-8714-84b15ee909f5" />


Question 7

Write a SQL query to calculate the final price after applying both the discount and the tax. Return product_id, original_price, discount_percentage, tax_rate, and final_price.
```
select product_id,original_price,discount_percentage,tax_rate,(original_price*(1-discount_percentage))*(1+tax_rate) as final_price
from products;
```
Output:

<img width="712" height="197" alt="image" src="https://github.com/user-attachments/assets/105b2628-084e-49a0-aff6-d95c686e0242" />

Question 8

Create a report that shows the capitalized FirstName and capitalized LastName renamed as FirstName and Lastname respectively and EmployeeId from the employees table sorted by EmployeeId in descending order.
```
select upper(FirstName) AS FirstName,upper(LastName) AS LastName,EmployeeId
from employees
order by EmployeeID desc;
```
Output:

<img width="402" height="546" alt="image" src="https://github.com/user-attachments/assets/2be9ec16-5bea-4dbc-8b79-19486ee82d3a" />


Question 9

Write a SQL statement to retrieve city(column name) of all customers from customers table without any repeats.
```
select distinct city from customers;
```
Output:

<img width="471" height="483" alt="image" src="https://github.com/user-attachments/assets/2c58bae9-6104-4d6a-98a6-6b6fa99285c0" />


Question 10

Write a SQL statement to Double the salary for employees in department 20 who have a job_id ending with 'MAN'
```
update EMPLOYEES
SET SALARY= SALARY *2
WHERE JOB_ID like'%MAN';
```
Output:

<img width="623" height="275" alt="image" src="https://github.com/user-attachments/assets/a49a543c-db0f-4da6-83ad-b25ac3993c4d" />

RESULT

Thus, the SQL queries to implement DML commands have been executed successfully.

Module 2 Grade:

<img width="1038" height="115" alt="image" src="https://github.com/user-attachments/assets/c9375723-ee8a-4a52-b554-ff294d51e9b3" />
