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
--Write a SQL statement to double the availability of the product with product_id 1.

products table

---------------
product_id
product_name
category_id
availability

```sql
--UPDATE products 
SET availability =availability *2
WHERE product_id=1;
```

**Output:**
<img width="510" height="230" alt="image" src="https://github.com/user-attachments/assets/80ad3d25-0f5a-4a66-a55d-a2d78d258b94" />


**Question 2**
---
--Write a SQL statement to Update the hire_date of employees in department 50 to 2024-01-24.

Employees table

---------------
employee_id
first_name
last_name
email
phone_number
hire_date
job_id
salary
commission_pct
manager_id
department_id

```sql
-- UPDATE employees
SET hire_date = '2024-01-24'
WHERE department_id =50;
```

**Output:**
<img width="500" height="228" alt="image" src="https://github.com/user-attachments/assets/9e03340c-3d26-41b9-9e1d-cc04388392bd" />


**Question 3**
---
-- Write a SQL statement to Double the salary for employees in department 20 who have a job_id ending with 'MAN'

Employees table

---------------
employee_id
first_name
last_name
email
phone_number
hire_date
job_id
salary
commission_pct
manager_id
department_id

```sql
-- UPDATE employees
SET salary = salary*2
WHERE department_id = 20
    AND job_id LIKE '%MAN%';
```

**Output:**
<img width="1303" height="280" alt="image" src="https://github.com/user-attachments/assets/123ffbac-961f-443c-a12b-368e1be069e4" />


**Question 4**
---
--Write a SQL query to Delete customers with 'GRADE' 3 and whose 'CUST_NAME' contains the substring 'BBB', and 'PAYMENT_AMT' is greater than 2000

Sample table: Customer

+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+  
|CUST_CODE  | CUST_NAME   | CUST_CITY   | WORKING_AREA | CUST_COUNTRY | GRADE | OPENING_AMT | RECEIVE_AMT | PAYMENT_AMT |OUTSTANDING_AMT| PHONE_NO     | AGENT_CODE |
+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+
| C00013    | Holmes      | London      | London       | UK           |     2 |     6000.00 |     5000.00 |     7000.00 |       4000.00 | BBBBBBB      | A003       |
| C00001    | Micheal     | New York    | New York     | USA          |     2 |     3000.00 |     5000.00 |     2000.00 |       6000.00 | CCCCCCC      | A008       |
| C00020    | Albert      | New York    | New York     | USA          |     3 |     5000.00 |     7000.00 |     6000.00 |       6000.00 | BBBBSBB      | A008       |
For example:

Test	Result
select changes();
changes()
----------
0


```sql
--DELETE FROM Customer
WHERE grade = 3
    AND cust_name LIKE '%BBB%'
    AND payment_amt > 2000;
```

**Output:**
<img width="1328" height="381" alt="image" src="https://github.com/user-attachments/assets/1a93c6da-cb95-4bbc-97d3-122c42163830" />


**Question 5**
---
--Write a SQL query to Delete customers from 'customer' table where 'AGENT_CODE' is either 'A003' or 'A008'.

 
Sample table: Customer

+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+  
|CUST_CODE  | CUST_NAME   | CUST_CITY   | WORKING_AREA | CUST_COUNTRY | GRADE | OPENING_AMT | RECEIVE_AMT | PAYMENT_AMT |OUTSTANDING_AMT| PHONE_NO     | AGENT_CODE |
+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+
| C00013    | Holmes      | London      | London       | UK           |     2 |     6000.00 |     5000.00 |     7000.00 |       4000.00 | BBBBBBB      | A003       |
| C00001    | Micheal     | New York    | New York     | USA          |     2 |     3000.00 |     5000.00 |     2000.00 |       6000.00 | CCCCCCC      | A008       |
| C00020    | Albert      | New York    | New York     | USA          |     3 |     5000.00 |     7000.00 |     6000.00 |       6000.00 | BBBBSBB      | A008       |
For example:

Test	Result
select distinct(agent_code)from customer;
AGENT_CODE
----------
A003
A008
A011
A006
A005
A010
A002
A004
A009
A007
A012
A001
AGENT_CODE
----------
A011
A006
A005
A010
A002
A004
A009
A007
A012
A001

```sql
-- DELETE FROM customer
WHERE agent_code IN('A003','A008');
```

**Output:**

<img width="592" height="783" alt="image" src="https://github.com/user-attachments/assets/9344432e-ac7f-4ccb-af05-206d561193b1" />


**Question 6**
---
-- Write a query to get all the records from EmployeePosition table who have joined in the year 2020.

EmpID

EmpPosition

DateOfJoining

Salary

1

Manager

01/05/2024

500000

2

Executive

02/05/2024

75000

 

 
 
 
 


For example:

Result
EmpID       EmpPosition  DateOfJoining  Salary
----------  -----------  -------------  ----------
1           Manager      2020-05-01     500000
2           Executive    2020-05-02     75000
1           Manager      2020-05-01     500000
2           Executive    2020-05-02     75000


```sql
-- SELECT *
FROM EmployeePosition
WHERE DateOfJoining BETWEEN '2020-01-01'
    AND '2020-12-31';
```

**Output:**
<img width="806" height="227" alt="image" src="https://github.com/user-attachments/assets/1ab28136-74e2-408a-bad5-84ed2fae1e81" />



**Question 7**
---
-- Write a SQL query to classify value2 in the Calculations table as 'Small', 'Medium', or 'Large' based on whether it is less than 10, between 10 and 50, or greater than 50, respectively.

cid         name        type        notnull     dflt_value  pk
----------  ----------  ----------  ----------  ----------  ----------
0           id          INTEGER     0                       1
1           value1      REAL        0                       0
2           value2      REAL        0                       0
3           base        INTEGER     0                       0
4           exponent    INTEGER     0                       0
5           number      REAL        0                       0
6           decimal     REAL        0                       0
 

For example:

Result
id          value2      size_category
----------  ----------  -------------
1           2.0         Small
2           5.0         Small
3           7.0         Small
4           9.0         Small


```sql
--SELECT id,
        value2,
        CASE
            WHEN value2<10 THEN 'Small'
            WHEN value2 BETWEEN 10 AND 50
THEN 'Medium'
            ELSE 'Large'
        END AS size_category
FROM Calculations;        
         
```

**Output:**

<img width="595" height="353" alt="image" src="https://github.com/user-attachments/assets/9854d4e9-0827-4975-948b-f7952b040cee" />


**Question 8**
---
-- Write a SQL query to find customers who are either from the city 'New York' or who have a grade greater than 200. Return customer_id, cust_name, city, grade, and salesman_id.

Sample table: customer

 customer_id |   cust_name    |    city    | grade | salesman_id 
-------------+----------------+------------+-------+-------------
        3002 | Nick Rimando   | New York   |   100 |        5001
        3007 | Brad Davis     | New York   |   200 |        5001
        3005 | Graham Zusi    | California |   200 |        5002
For example:

Result
customer_id  cust_name     city        grade       salesman_id
-----------  ------------  ----------  ----------  -----------
3004         Fabian Johns  Paris       300         5006
3007         Brad Davis    New York    200         5001
3008         Julian Green  London      300         5002

```sql
--SELECT customer_id ,cust_name,city,grade,salesman_id
FROM Customer
WHERE city = 'New York'
    OR grade > 200;
```

**Output:**
<img width="1118" height="329" alt="image" src="https://github.com/user-attachments/assets/1358075f-d4e3-4ff6-a572-50ee53c2e5eb" />


**Question 9**
---
-- Write a query to list all products where the discount amount exceeds $50. The discount amount is calculated as original_price * discount_percentage. Return product_id, original_price, discount_percentage, and discount_amount.

Sample table: Products

product_id | original_price | discount_percentage

-----------------------------------------------------------

"101" "50" "0.1"

"102" "150" "0.15"

"103" "200" "0.2"

"104" "300" "0.25"

 

 

For example:

Result
product_id  original_price  discount_percentage  discount_amount
----------  --------------  -------------------  ---------------
104         300.0           0.25                 75.0

```sql
--SELECT product_id,original_price,discount_percentage,
       original_price * discount_percentage AS discount_amount
FROM Products
WHERE original_price * discount_percentage > 50;
```

**Output:**
<img width="1133" height="187" alt="image" src="https://github.com/user-attachments/assets/01c8354c-e35e-405e-adeb-0bbf052d2fd4" />



**Question 10**
---
--Write a SQL query to calculate the number of years each employee has been with the company till '2024-08-30'.

Calculations table

cid         name        type        
----------  ----------  ---------- 
0           empno       INT         
1           ename       VARCHAR(100)
2           job         VARCHAR(50)
3           mgr         INT        
4           hiredate    DATE        
5           sal         DECIMAL(10,2)  
6           comm        DECIMAL(10,2)  
7           deptno      INT         
For example:

Result
ename       Tenure
----------  ----------
JONES       43
MARTIN      42
BLAKE       43
CLARK       43
SCOTT       41
KING        42
TURNER      42


```sql
-- SELECT ename,
       CAST((julianday( '2024-08-30')-julianday(hiredate))/365.25 AS INTEGER)AS Tenure
FROM emp;       
```

**Output:**

<img width="498" height="298" alt="image" src="https://github.com/user-attachments/assets/9ace8352-7f24-4ab7-b26c-14e6fcfaf042" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
