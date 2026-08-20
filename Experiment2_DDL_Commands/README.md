# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--
<img width="827" height="276" alt="image" src="https://github.com/user-attachments/assets/b6afaa3a-6484-4066-935c-1b8bb904b423" />


```sql
ALTER TABLE student_details
ADD column Date_of_birth Date;
```

**Output:**
<img width="953" height="174" alt="image" src="https://github.com/user-attachments/assets/04d73612-ae46-484e-941d-73cdc3c7d9ce" />



**Question 2**
---
<img width="711" height="173" alt="image" src="https://github.com/user-attachments/assets/df1a833a-cb3b-4a33-833c-dde4bb1842f9" />


```sql
create table Department(
    DepartmentID integer PRIMARY KEY,DepartmentName TEXT UNIQUE NOT NULL,
    Location text );

```

**Output:**

<img width="1208" height="167" alt="image" src="https://github.com/user-attachments/assets/4ca7e64d-ec01-4dc4-a392-0bcd87f70e45" />


**Question 3**
---
<img width="1307" height="453" alt="image" src="https://github.com/user-attachments/assets/2ece9fe2-cbd5-4755-90f5-abba430bd473" />


```sql
DELETE FROM customer
WHERE cust_city LIKE 'L%';
```

**Output:**

<img width="1173" height="371" alt="image" src="https://github.com/user-attachments/assets/eb82b7cc-4b68-4401-8bc5-948e9c7259ca" />


**Question 4**
---
<img width="686" height="309" alt="image" src="https://github.com/user-attachments/assets/3e7b5e6f-624c-4dfe-8507-e66bb383ccf0" />


```sql
create table item(item_id text primary key,item_desc text not null,rate integer not null,
icom_id text(4),foreign key (icom_id)references company(com_id) on update cascade on delete cascade);
```

**Output:**

<img width="1078" height="270" alt="image" src="https://github.com/user-attachments/assets/c67a27e5-d76c-4a3c-b9a7-bdc1f135971a" />

**Question 5**
---
<img width="753" height="317" alt="image" src="https://github.com/user-attachments/assets/d4bd9cba-3282-40bd-ab6c-3899c8e23844" />


```sql
create table item(item_id text primary key,item_desc text not null,rate integer not null,icom_id text(4),foreign key (icom_id)references company(com_id) on update set null on delete set null);
```

**Output:**
<img width="1099" height="240" alt="image" src="https://github.com/user-attachments/assets/1ad1cda0-a191-4f76-a129-0757bb573252" />



**Question 6**
---
<img width="819" height="193" alt="image" src="https://github.com/user-attachments/assets/57cd0cd6-708f-4f2a-a4da-a93a0f1c252a" />


```sql
CREATE TABLE Attendance(
AttendanceID  INTEGER  primary key,
EmployeeID INTEGER , 
AttendanceDate  DATE,
Status  TEXT check (status in( 'Present', 'Absent', 'Leave')),
foreign key (EmployeeID) references Employees(EmployeeID)
);
```

**Output:**
<img width="1079" height="175" alt="image" src="https://github.com/user-attachments/assets/82037f0a-5cf7-4859-b463-34803ce63d6a" />



**Question 7**
---
<img width="1280" height="293" alt="image" src="https://github.com/user-attachments/assets/5b0eb4fd-56e2-40a1-b61d-dee8fddaa6f5" />


```sql
ALTER TABLE Companies 
ADD COLUMN designation varchar(50);
ALTER TABLE Companies 
ADD COLUMN net_salary number;
```

**Output:**
<img width="1194" height="283" alt="image" src="https://github.com/user-attachments/assets/65d4f1a9-9916-4218-af13-89c0adfe2e5e" />



**Question 8**
---
<img width="1279" height="375" alt="image" src="https://github.com/user-attachments/assets/61cbb9a9-93f0-4328-ad96-bb8a240866bb" />


```sql
delete from customer where cust_city <> 'New York' and OUTSTANDING_AMT>5000;

```

**Output:**

<img width="1357" height="311" alt="image" src="https://github.com/user-attachments/assets/4d8c309b-dc09-4c1d-8c86-fe310e0e04d4" />


**Question 9**
---
<img width="677" height="258" alt="image" src="https://github.com/user-attachments/assets/e35b16e4-c9b4-44ae-a459-ea5732afb7bb" />


```sql
create table orders (OrderID INTEGER,OrderDate TEXT,CustomerID INTEGER);
```

**Output:**
<img width="1249" height="285" alt="image" src="https://github.com/user-attachments/assets/5f72431b-c30e-493d-9a87-3f388f3cb9f8" />


**Question 10**
---
<img width="637" height="371" alt="image" src="https://github.com/user-attachments/assets/97f632e5-674a-4cc7-aa57-a5d17391a93e" />

```sql
delete from doctors where doctor_id between 2 and 4;


```

**Output:**

<img width="979" height="672" alt="image" src="https://github.com/user-attachments/assets/3a5bb9ba-bc84-430d-b554-05936afa61af" />




## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
