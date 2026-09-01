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
-- How many doctors specialize in each medical specialty?

Sample table:Doctors Table



For example:

Result
Specialty          TotalDocto
-----------------  ----------
Gastroenterology   1
Neurology          1
Obstetrics         3
Ophthalmology      1
Orthopedics        1
Pediatrics         2
Urology            1

```sql
-- SELECT Specialty,COUNT(*)AS TotalDoctors
FROM Doctors
GROUP BY Specialty;
```

**Output:**

<img width="1062" height="665" alt="image" src="https://github.com/user-attachments/assets/5d10283a-f70b-444f-bcf4-ee74c011f985" />


**Question 2**
---
-- What is the total number of appointments scheduled for each day?

Table: Appointments

name                 type
-------------------  ----------
AppointmentID        INTEGER
PatientID            INTEGER
DoctorID             INTEGER
AppointmentDateTime  DATETIME
Purpose              TEXT
Status               TEXT
 

For example:

Result
AppointmentDate  TotalAppointments
---------------  -----------------
2024-02-16       4
2024-02-18       1
2024-02-20       1
2024-02-21       1
2024-02-22       1
2024-02-23       2

```sql
-- SELECT DATE (AppointmentDateTime)AS AppointmentDate,
COUNT(*)As TotalAppointments
FROM Appointments
GROUP BY DATE(AppointmentDateTime)
ORDER BY AppointmentDate;
```

**Output:**
<img width="832" height="651" alt="image" src="https://github.com/user-attachments/assets/b928e69b-2cff-4a7b-9007-0ec43b0a972b" />



**Question 3**
---
-- How many appointments are scheduled for each patient?

Sample table: Appointments Table

name                  type
--------------------  ----------
AppointmentID         INTEGER
PatientID             INTEGER
DoctorID              INTEGER
AppointmentDateTime   DATETIME
Purpose               TEXT
Status                TEXT
For example:

Result
PatientID   TotalAppointments
----------  -----------------
3           3
5           2
6           1
7           1
10          3


```sql
--SELECT PatientID,
COUNT(*)AS TotalAppointments
FROM Appointments
GROUP BY PatientID
ORDER BY PatientID;
```

**Output:**

<img width="1057" height="640" alt="image" src="https://github.com/user-attachments/assets/feab2a0e-b79c-4174-b2bb-6be721e81056" />


**Question 4**
---
-- Write a SQL query to return the total number of rows in the 'customer' table where the city is not Noida.

Sample table: customer



 

For example:

Result
COUNT
----------
9


```sql
--SELECT COUNT(*)AS COUNT
FROM customer
WHERE city <> 'Noida';
```

**Output:**

<img width="406" height="346" alt="image" src="https://github.com/user-attachments/assets/2085b092-bb60-45c2-8b16-d0457b86b8e0" />


**Question 5**
---
-- Write a SQL query to find the youngest employee in the company?

Table: employee

name        type
----------  ----------
id          INTEGER
name        TEXT
age         INTEGER
city        TEXT
income      INTEGER
 

For example:

Result
Employee_Name  Age
-------------  ----------
Peter          32


```sql
--SELECT name AS Employee_Name,age AS Age
FROM employee
ORDER BY age ASC
LIMIT 1;
```

**Output:**

<img width="692" height="322" alt="image" src="https://github.com/user-attachments/assets/cc31f6d0-78e1-4a28-9373-29eae015754d" />


**Question 6**
---
--Write a SQL query to determine the number of customers who received at least one grade for their activity.

Sample table: customer

customer_id |   cust_name    |    city    | grade | salesman_id 

-------------+----------------+------------+-------+-------------

        3002 | Nick Rimando   | New York   |   100 |        5001

        3007 | Brad Davis     | New York   |   200 |        5001

        3005 | Graham Zusi    | California |   200 |        5002

 

For example:

Result
COUNT
----------
8


```sql
--SELECT COUNT(*) AS COUNT
FROM customer
WHERE grade IS NOT NULL;

```

**Output:**

<img width="387" height="352" alt="image" src="https://github.com/user-attachments/assets/be4126f8-b967-4f48-9c77-f675b90a67e7" />


**Question 7**
---
-- Write a SQL query to find the customer with longest name?

Table: customer

name        type
----------  ----------
id          INTEGER
name        TEXT
city        TEXT
email       TEXT
phone       INTEGER
For example:

Result
name          length
------------  ----------
Preeti Patel  12


```sql
-- SELECT name,LENGTH(name)AS length
FROM customer
ORDER BY LENGTH(name)DESC
LIMIT 1;
```

**Output:**

<img width="732" height="347" alt="image" src="https://github.com/user-attachments/assets/50da63af-7672-4f7e-8bad-324bfc60d7b1" />


**Question 8**
---
-- Write the SQL query that achieves the selection of product names and the maximum price for each category from the "products" table, and includes only those products where the maximum price is greater than 15.

Sample table: products



For example:

Result
category_id  product_name  Price
-----------  ------------  ----------
1            Orange        15.5
2            Monitor       25

```sql
-- SELECT category_id,
product_name,
MAX(price)AS Price
FROM products
GROUP BY category_id
HAVING MAX(price)>15;
```

**Output:**

<img width="1015" height="441" alt="image" src="https://github.com/user-attachments/assets/9334e9ba-1b64-4c69-949a-616027bd6f31" />


**Question 9**
---
--Write the SQL query that accomplishes the selection of product which has lowest price in each category from the "products" table and includes only those products where the minimum price is less than 10.

Sample table: products



For example:

Result
category_id  Price
-----------  ----------
3            7.5


```sql
--SELECT category_id,
MIN(price)AS Price
FROM products
GROUP BY category_id
HAVING MIN(price)<10;
```

**Output:**

<img width="737" height="382" alt="image" src="https://github.com/user-attachments/assets/68de6f44-c4c8-474c-9374-85aaa36fc15b" />


**Question 10**
---
-- Write the SQL query that accomplishes the grouping of data by joining date (jdate), calculates the minimum work hours for each date, and excludes dates where the minimum work hour is not less than 10.

Sample table: employee1



For example:

Result
jdate       MIN(workhour)
----------  -------------
2002.0      9
2004.0      9
2006.0      9


```sql
-- SELECT jdate,
            MIN(workhour)
FROM employee1
GROUP BY jdate
ORDER BY jdate;
```

**Output:**

<img width="782" height="462" alt="image" src="https://github.com/user-attachments/assets/48fdcb90-95b9-4502-959c-d5c6f6e8b76d" />


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
