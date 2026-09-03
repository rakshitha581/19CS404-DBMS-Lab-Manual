# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
--
<img width="652" height="449" alt="image" src="https://github.com/user-attachments/assets/58edbd77-ad13-4ffa-8dfa-d3c7f69104f7" />


```sql
SELECT 
    DATE(AppointmentDateTime) AS AppointmentDate,
    COUNT(*) AS TotalAppointments
FROM 
    Appointments
GROUP BY 
    DATE(AppointmentDateTime)
ORDER BY 
    AppointmentDate;
```

**Output:**

<img width="735" height="502" alt="image" src="https://github.com/user-attachments/assets/cfeac3a9-9c29-418e-9569-790793e8fce8" />


**Question 2**
---
<img width="772" height="433" alt="image" src="https://github.com/user-attachments/assets/14548955-1463-46d7-b7fb-3aae476d898e" />


```sql
SELECT
  Medication,
  AVG(Dosage) AS AvgDosage
FROM
  Prescriptions
GROUP BY
  Medication
ORDER BY
  Medication;
```

**Output:**
<img width="603" height="562" alt="image" src="https://github.com/user-attachments/assets/6bf1209b-c36e-4ea5-b451-e753c64402a3" />


**Question 3**
---
<img width="836" height="336" alt="image" src="https://github.com/user-attachments/assets/bee82026-0456-49ef-8026-00600373dda1" />


```sql
SELECT
  strftime('%Y-%m', Date) AS Month,
  COUNT(*) AS TotalRecords
FROM
  MedicalRecords
GROUP BY
  Month
ORDER BY
  Month;
```

**Output:**
<img width="763" height="358" alt="image" src="https://github.com/user-attachments/assets/42fe1a37-69be-4e44-8898-4934772f2335" />



**Question 4**
---
<img width="745" height="327" alt="image" src="https://github.com/user-attachments/assets/0bb9dc2e-51dc-4f19-acee-45c6dbe88d50" />

```sql
SELECT SUM(purch_amt) AS TOTAL
FROM orders;
```

**Output:**

<img width="775" height="274" alt="image" src="https://github.com/user-attachments/assets/7299a8cb-694a-4f61-8ec6-32b2fc40898e" />


**Question 5**
---
<img width="754" height="328" alt="image" src="https://github.com/user-attachments/assets/bb48f60a-fc0c-4433-92e4-4690ac883bdc" />


```sql
SELECT SUM(income) AS total_income
FROM employee
WHERE age >= 40;
```

**Output:**
<img width="827" height="274" alt="image" src="https://github.com/user-attachments/assets/55a9ced3-ec23-44c4-b629-1f129c0e8fac" />



**Question 6**
---
<img width="721" height="349" alt="image" src="https://github.com/user-attachments/assets/74062023-c008-4b66-afe0-0091279c8365" />


```sql

SELECT name AS Employee_Name, age AS Age
FROM employee
ORDER BY age ASC, id ASC
LIMIT 1;
```

**Output:**

<img width="873" height="271" alt="image" src="https://github.com/user-attachments/assets/6a8fa633-052b-46a5-b5a5-98fb124b1579" />


**Question 7**
---
<img width="710" height="369" alt="image" src="https://github.com/user-attachments/assets/9a7136b2-778d-4fcb-b685-90cacf4079fd" />


```sql
SELECT SUM(inventory) AS total
FROM fruits
WHERE unit = 'LB';
```

**Output:**
<img width="865" height="276" alt="image" src="https://github.com/user-attachments/assets/09186a6b-e0d2-4ac7-aa3f-2929af3359a9" />

**Question 8**
---
<img width="742" height="347" alt="image" src="https://github.com/user-attachments/assets/fed94477-f755-470c-95ad-7c772f1aeb2c" />


```sql
SELECT PatientID, COUNT(*) AS TotalRecords
FROM MedicalRecords
GROUP BY PatientID
HAVING COUNT(*) > 3;
```

**Output:**
<img width="907" height="286" alt="image" src="https://github.com/user-attachments/assets/8e3f5792-0ca3-42de-8924-36aead6572ce" />


**Question 9**
---
<img width="832" height="301" alt="image" src="https://github.com/user-attachments/assets/9be262df-180d-46ce-b6a0-647b6780e054" />


```sql
SELECT Diagnosis, COUNT(*) AS DiagnosisCount
FROM MedicalRecords
GROUP BY Diagnosis
ORDER BY DiagnosisCount DESC
LIMIT 1;
```

**Output:**
<img width="836" height="273" alt="image" src="https://github.com/user-attachments/assets/7d722ae2-9303-4ad8-9c87-0f8f4af56b6c" />



**Question 10**
---
<img width="872" height="368" alt="image" src="https://github.com/user-attachments/assets/d96e21f2-6e91-4dac-99df-b7ee68d6c9b9" />


```sql
SELECT DoctorID, COUNT(AppointmentID) AS TotalAppointments
FROM Appointments
GROUP BY DoctorID;
```

**Output:**

<img width="892" height="481" alt="image" src="https://github.com/user-attachments/assets/455c4822-2ea7-4854-b0fe-a3db622db798" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
