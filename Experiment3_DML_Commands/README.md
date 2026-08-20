# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
Write a SQL statement to Update the product_name to 'Premium Bread' whose product ID is 5 in the products table.

```sql
UPDATE Products SET product_name = 'Premium Bread'
WHERE product_id = 5;
```

**Output:**
<img width="1196" height="488" alt="image" src="https://github.com/user-attachments/assets/509ce58e-a52c-4e72-9123-db354b39ce95" />



**Question 2**
---
Write a SQL statement to Update the per_unit_price to 25 and total_price accordingly in purchases table where purchase_date is '2022-08-15' and product_id is 12.

```sql
UPDATE purchases 
SET per_unit_price = 25,
total_price = quantity *25
WHERE purchase_date='2022-08-15' AND product_id = 12;
```

**Output:**
<img width="1210" height="605" alt="image" src="https://github.com/user-attachments/assets/d2fa66af-d742-480f-8dba-ca8b3efb2017" />


**Question 3**
---
Update the 'Selling_Price' to add 10% extra margin for all products supplied by the supplier with id 6.

PRODUCTS TABLE

name type

product_id INT product_name VARCHAR(100) category VARCHAR(50) cost_price DECIMAL(10,2) sell_price DECIMAL(10,2) reorder_lvl INT quantity INT supplier_id INT

```sql
UPDATE Products 
SET sell_price = sell_price+ (sell_price*0.10) 
WHERE supplier_id=6;
```

**Output:**
<img width="1203" height="634" alt="image" src="https://github.com/user-attachments/assets/7e117c77-30db-44d2-9e9f-059b3bec6f6b" />



**Question 4**
---
Write a SQL statement to Update the hire_date of employees in department 50 to 2024-01-24

```sql

UPDATE Employees
SET hire_date = '2024-01-24'
WHERE department_id = 50 ;

 
```

**Output:**

<img width="1200" height="377" alt="image" src="https://github.com/user-attachments/assets/171c9c4c-00af-4043-8f80-20843b5ade31" />


**Question 5**
---
Write a SQL query to Delete a Specific Surgery whose ID is 3

Sample table: Surgeries

```sql
DELETE FROM Surgeries
WHERE surgery_id = 3;
```

**Output:**
<img width="1215" height="449" alt="image" src="https://github.com/user-attachments/assets/e04da850-7340-455d-a3cc-3b993369fdc2" />


**Question 6**
---
Write a SQL query to remove rows from the table 'customer' with the following condition -

1.'cust_city' should begin with the letter 'L',
Sample table: Customer

```sql
DELETE FROM customer
WHERE cust_city LIKE'L%';
```

**Output:**
<img width="1202" height="813" alt="image" src="https://github.com/user-attachments/assets/cadf45fb-0707-4b63-90bc-61906f8aca72" />


**Question 7**
---
--Write a SQL query to delete a doctor from Doctors table whose Specialization is 'Pediatrics' and First name is 'Michael'.

Sample table: Doctors
```sql
DELETE FROM Doctors
WHERE
specialization ='Pediatrics'AND first_name = 'Michael';
```

**Output:**
<img width="1200" height="474" alt="image" src="https://github.com/user-attachments/assets/36cbe71d-24be-486f-90fa-a2079bbed987" />


**Question 8**
---

Write a SQL query to Select all patients whose name starts with A.

Table: Patients

name type

patient_id INT first_name VARCHAR(50) last_name VARCHAR(50) date_of_birth DATE admission_date DATE discharge_date DATE doctor_id INT
```sql
SELECT * FROM Patients
WHERE first_name LIKE 'A%';
```

**Output:**
<img width="1216" height="468" alt="image" src="https://github.com/user-attachments/assets/21175394-7cba-40bd-82e4-f133f5ac5cf1" />



**Question 9**
---

Write a SQL query to categorize decimal as 'High', 'Medium', or 'Low' based on whether it is greater than 100, between 50 and 100, or less than 50 in the Calculations table

cid name type notnull dflt_value pk

0 id INTEGER 0 1 1 value1 REAL 0 0 2 value2 REAL 0 0 3 base INTEGER 0 0 4 exponent INTEGER 0 0 5 number REAL 0 0 6 decimal REAL 0 0
```sql
SELECT id,decimal,
case
    when decimal> 100 then 'High'
    when decimal BETWEEN 50 and 100  then 'Medium'
    ELSE 'Low'
    END AS category
    from Calculations;
```

**Output:**
<img width="1227" height="548" alt="image" src="https://github.com/user-attachments/assets/f9c89701-94ba-4a4f-80de-ff215b99ef32" />


**Question 10**
---
Write a SQL query to find customers who are either from the city 'New York' or who have a grade greater than 200. Return customer_id, cust_name, city, grade, and salesman_id.

Sample table: customer

customer_id | cust_name | city | grade | salesman_id -------------+----------------+------------+-------+------------- 3002 | Nick Rimando | New York | 100 | 5001 3007 | Brad Davis | New York | 200 | 5001 3005 | Graham Zusi | California | 200 | 5002

```sql
SELECT customer_id, cust_name, city, grade,salesman_id FROM customer
WHERE City = 'New York' OR GRADE >200;
```

**Output:**
<img width="1189" height="554" alt="image" src="https://github.com/user-attachments/assets/ef8701f6-27fd-450d-a2df-ae45a89d417c" />



## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
