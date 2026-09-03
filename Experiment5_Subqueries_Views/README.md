# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
--
<img width="1026" height="542" alt="image" src="https://github.com/user-attachments/assets/03fb79aa-d69d-45d2-bc7d-43d8a8d6e443" />


```sql
SELECT ord_no, purch_amt, ord_date, salesman_id
FROM orders
WHERE salesman_id IN (
    SELECT salesman_id
    FROM salesman
    WHERE commission = (SELECT MAX(commission) FROM salesman)
);

```

**Output:**
<img width="904" height="380" alt="image" src="https://github.com/user-attachments/assets/272058e8-76a9-46a7-90b1-11fa1538b814" />


**Question 2**
---
<img width="1042" height="547" alt="image" src="https://github.com/user-attachments/assets/428734fd-d5c6-4424-87ff-5e1a3a9e5785" />

```sql
SELECT ord_no, purch_amt, ord_date, customer_id, salesman_id
FROM orders
WHERE salesman_id IN (
    SELECT salesman_id
    FROM salesman
    WHERE city = 'New York'
);

```

**Output:**

<img width="917" height="374" alt="image" src="https://github.com/user-attachments/assets/aca19735-b52a-461b-96fe-a4eca792003c" />

**Question 3**
---
<img width="1022" height="495" alt="image" src="https://github.com/user-attachments/assets/cd341313-e6b9-40bf-81a8-efcc217a346b" />

```sql
SELECT o.ord_no, o.purch_amt, o.ord_date, o.customer_id, o.salesman_id
FROM orders o
JOIN salesman s ON o.salesman_id = s.salesman_id
WHERE s.name = 'Paul Adam';

```

**Output:**

<img width="986" height="319" alt="image" src="https://github.com/user-attachments/assets/f8b46f6c-e520-4808-9aef-ee9320f253c3" />


**Question 4**
---
<img width="871" height="375" alt="image" src="https://github.com/user-attachments/assets/77dc6303-5d5d-4709-8fd3-a728b426a868" />


```sql
SELECT name, city
FROM customer
WHERE city IN (
    SELECT city
    FROM customer
    WHERE id IN (3, 7)
);

```

**Output:**

<img width="814" height="369" alt="image" src="https://github.com/user-attachments/assets/6f788ea8-ca8c-4cfa-9dac-4a47113d9755" />


**Question 5**
---
<img width="1082" height="527" alt="image" src="https://github.com/user-attachments/assets/32453b4c-5e88-48dc-b146-30f7db7b1a58" />


```sql
SELECT ord_no, purch_amt, ord_date, customer_id, salesman_id
FROM orders
WHERE salesman_id IN (
    SELECT salesman_id
    FROM salesman
    WHERE city = 'New York'
);

```

**Output:**

<img width="980" height="386" alt="image" src="https://github.com/user-attachments/assets/12a91e99-6599-48c0-852b-bebc51452a44" />


**Question 6**
---
<img width="768" height="432" alt="image" src="https://github.com/user-attachments/assets/373827cb-fe9a-4f24-8de4-978d9c549f84" />


```sql
SELECT *
FROM CUSTOMERS
WHERE SALARY = 1500;

```

**Output:**

<img width="963" height="291" alt="image" src="https://github.com/user-attachments/assets/f0e7e541-7fd2-42b7-88d6-12c67af0bb31" />

**Question 7**
---
<img width="1012" height="437" alt="image" src="https://github.com/user-attachments/assets/92a19e18-3804-4a63-81c7-dc46d8ac0644" />


```sql
SELECT student_name, grade
FROM GRADES g
WHERE grade = (
    SELECT MAX(grade)
    FROM GRADES
    WHERE subject = g.subject
);

```

**Output:**
<img width="692" height="356" alt="image" src="https://github.com/user-attachments/assets/3385e379-1423-45f6-8207-447294d4e65f" />



**Question 8**
---
<img width="971" height="429" alt="image" src="https://github.com/user-attachments/assets/d984668b-2024-477b-a75c-f9316ac6cc84" />

```sql
SELECT student_name, grade
FROM GRADES g
WHERE grade = (
    SELECT MIN(grade)
    FROM GRADES
    WHERE subject = g.subject
);


```

**Output:**
<img width="774" height="353" alt="image" src="https://github.com/user-attachments/assets/110ea43f-53f0-4579-b558-e1772aefbde5" />



**Question 9**
---
<img width="863" height="364" alt="image" src="https://github.com/user-attachments/assets/b01d2405-b212-4855-a30a-8315f92c6a41" />

```sql
SELECT *
FROM customer
WHERE city <> (
    SELECT city
    FROM customer
    WHERE id = (SELECT MAX(id) FROM customer)
);

```

**Output:**
<img width="1134" height="386" alt="image" src="https://github.com/user-attachments/assets/5d6a04f5-5a0d-4a4b-80a0-d706e703f11d" />



**Question 10**
---
<img width="1210" height="378" alt="image" src="https://github.com/user-attachments/assets/1a363c36-746b-4ab9-a296-927df3198fa9" />


```sql
SELECT *
FROM orders
WHERE salesman_id IN (
    SELECT DISTINCT salesman_id
    FROM orders
    WHERE customer_id = 3007
);

```

**Output:**


<img width="1038" height="353" alt="image" src="https://github.com/user-attachments/assets/92427119-6b7c-41c1-b455-4bb85447714c" />


## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
