# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
--
<img width="1371" height="274" alt="image" src="https://github.com/user-attachments/assets/09efbca2-7edf-42ee-b015-f90a683a08e6" />

```sql
SELECT c.*
FROM customer c
LEFT JOIN orders o ON c.customer_id = o.customer_id
WHERE o.ord_date BETWEEN '2012-07-01' AND '2012-07-30';

```

**Output:**
<img width="1148" height="332" alt="image" src="https://github.com/user-attachments/assets/0a999c2d-b0d1-402c-9da3-39138de82039" />



**Question 2**
---
<img width="1334" height="459" alt="image" src="https://github.com/user-attachments/assets/926d2acc-c809-4e02-ac50-a1ecdcbb89e0" />


```sql
SELECT n.*
FROM nurses n
INNER JOIN departments d ON n.department_id = d.department_id
WHERE d.department_name = 'Pediatrics';

```

**Output:**
<img width="989" height="332" alt="image" src="https://github.com/user-attachments/assets/b18aa837-b939-4bbd-ac2c-bdf5f1985166" />



**Question 3**
---
<img width="1070" height="659" alt="image" src="https://github.com/user-attachments/assets/d0aae1c5-dfe7-4afc-bd69-9dab7ddc938c" />


```sql
SELECT 
    c.cust_name AS "Customer Name",
    c.city,
    s.name AS "Salesman",
    s.commission
FROM customer c
INNER JOIN salesman s ON c.salesman_id = s.salesman_id;

```

**Output:**
<img width="1084" height="673" alt="image" src="https://github.com/user-attachments/assets/3897064e-4deb-425b-93b2-046c847eadb9" />


**Question 4**
---
<img width="957" height="598" alt="image" src="https://github.com/user-attachments/assets/d3222048-2dd3-4c06-8e38-600b21241868" />

```sql
SELECT s.name AS "Salesman",
       c.cust_name,
       s.city
FROM salesman s
INNER JOIN customer c ON s.city = c.city;

```

**Output:**
<img width="912" height="525" alt="image" src="https://github.com/user-attachments/assets/92cbfcaa-87ae-416f-b5c2-2e928f581c6b" />


**Question 5**
---
<img width="1323" height="490" alt="image" src="https://github.com/user-attachments/assets/b8fbb88c-25dc-4093-aa54-29bb3be5b512" />

```sql
SELECT 
    p.first_name AS patient_name,
    d.first_name AS doctor_name
FROM patients p
INNER JOIN doctors d ON p.doctor_id = d.doctor_id
WHERE p.discharge_date IS NULL;


```

**Output:**
<img width="814" height="375" alt="image" src="https://github.com/user-attachments/assets/d420387a-1f6e-4b94-865f-266d551f6b2a" />



**Question 6**
---
<img width="1257" height="619" alt="image" src="https://github.com/user-attachments/assets/7804cb6c-8348-4814-b821-b9687f8c8d5a" />


```sql
SELECT 
    c.cust_name AS "Customer Name",
    c.city,
    s.name AS "Salesman",
    s.commission
FROM customer c
INNER JOIN salesman s ON c.salesman_id = s.salesman_id
WHERE s.commission > 0.12;

```

**Output:**

<img width="1071" height="580" alt="image" src="https://github.com/user-attachments/assets/5d83cdf6-b20e-4c7a-b6f5-ec5ad9941d34" />


**Question 7**
---
<img width="1171" height="341" alt="image" src="https://github.com/user-attachments/assets/6ff27744-efdb-4bb3-9d9f-df609a5b9ad5" />

```sql
SELECT p.*
FROM patients p
INNER JOIN appointments a ON p.patient_id = a.patient_id
WHERE a.appointment_date BETWEEN '2024-02-01' AND '2024-02-28';

```

**Output:**
<img width="1132" height="254" alt="image" src="https://github.com/user-attachments/assets/e1582b37-312c-42b8-a673-1c4a42fcc9fd" />



**Question 8**
---

<img width="1255" height="322" alt="image" src="https://github.com/user-attachments/assets/31bd84fa-660c-4d9b-8701-0c03b311af9d" />

```sql
SELECT 
    c.cust_name,
    o.ord_no,
    o.ord_date,
    o.purch_amt
FROM customer c
LEFT JOIN orders o ON c.customer_id = o.customer_id;

```

**Output:**

<img width="791" height="652" alt="image" src="https://github.com/user-attachments/assets/572a549b-3f76-44e2-99cd-ae513b031cb1" />


**Question 9**
---
<img width="1046" height="476" alt="image" src="https://github.com/user-attachments/assets/ccae19df-a17e-4fdf-9dd2-a58fa8c9762a" />


```sql
SELECT 
    c.cust_name,
    c.city AS city,
    c.grade,
    s.name AS Salesman,
    s.city AS city
FROM customer c
INNER JOIN salesman s ON c.salesman_id = s.salesman_id
WHERE c.grade < 300
ORDER BY c.customer_id ASC;

```

**Output:**

<img width="930" height="432" alt="image" src="https://github.com/user-attachments/assets/3d74f092-2cde-44e0-82ce-9572a7699d35" />


**Question 10**
---
<img width="1270" height="441" alt="image" src="https://github.com/user-attachments/assets/88d8d360-7629-4bef-bd9a-dca058b3edc7" />


```sql
SELECT 
    c.cust_name AS "Customer Name",
    c.city AS "city",
    s.name AS "Salesman",
    s.city AS "city",
    s.commission
FROM customer c
INNER JOIN salesman s ON c.salesman_id = s.salesman_id
WHERE c.city <> s.city
  AND s.commission > 0.12;

```

**Output:**

<img width="960" height="364" alt="image" src="https://github.com/user-attachments/assets/5a744ff4-f42e-4165-b703-b7a6a136255f" />



## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
