# Experiment 9: PL/SQL – Procedures and Functions

## AIM
To understand and implement procedures and functions in PL/SQL for performing various operations such as calculations, decision-making, and looping.

---

## THEORY

PL/SQL (Procedural Language/SQL) extends SQL by adding procedural constructs like variables, conditions, loops, procedures, and functions. Procedures and functions are subprograms that help modularize the code and improve reusability.

### **Procedure**
A PL/SQL **procedure** is a subprogram that performs a specific action. It does not return a value directly but can return values using `OUT` parameters.

**Syntax:**
```sql
CREATE OR REPLACE PROCEDURE procedure_name (parameters)
IS
BEGIN
   -- statements
END;
```

To call the procedure

```sql
EXEC procedure_name(arguments);
```

### **Function**
A PL/SQL **function** is a subprogram that returns a single value using the RETURN keyword.

```sql
CREATE OR REPLACE FUNCTION function_name (parameters)
RETURN datatype
IS
BEGIN
   -- statements
   RETURN value;
END;
```

To call the function:

```sql
SELECT function_name(arguments) FROM DUAL;
```

Key Differences:

-A procedure does not return a value, whereas a function must return a value.
-Functions can be called from SQL queries, procedures cannot (in most cases).

## 1. Write a PL/SQL Procedure to Find the Square of a Number

### Steps:
- Create a procedure named `find_square`.
- Declare a parameter to accept a number.
- Inside the procedure, compute the square of the input number.
- Use `DBMS_OUTPUT.PUT_LINE` to display the result.
- Call the procedure with a number as input.

**Expected Output:**  
Square of 6 is 36
<img width="707" height="227" alt="image" src="https://github.com/user-attachments/assets/a8186125-10da-4e78-8e88-9c6a40be08e8" />
<img width="238" height="87" alt="image" src="https://github.com/user-attachments/assets/2d5fab01-3d0b-401b-9b06-1f0940fd404a" />

---

## 2. Write a PL/SQL Function to Return the Factorial of a Number

### Steps:
- Create a function named `get_factorial`.
- Declare a parameter to accept a number.
- Use a loop to calculate the factorial.
- Return the result using the `RETURN` statement.
- Call the function using a `SELECT` statement or in an anonymous block.

**Expected Output:**  
Factorial of 5 is 120
<img width="627" height="477" alt="image" src="https://github.com/user-attachments/assets/6e3e3400-e506-4463-a533-58d9acd455d9" />
<img width="232" height="106" alt="image" src="https://github.com/user-attachments/assets/c861430b-9b2d-4205-889a-a59710fe1aad" />

---

## 3. Write a PL/SQL Procedure to Check Whether a Number is Even or Odd

### Steps:
- Create a procedure named `check_even_odd`.
- Accept an input parameter.
- Use the `MOD` function to check if the number is divisible by 2.
- Display whether it is Even or Odd using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
12 is Even
<img width="595" height="282" alt="image" src="https://github.com/user-attachments/assets/4843f747-f94d-4bb9-a529-cd7a1fabc742" />
<img width="140" height="97" alt="image" src="https://github.com/user-attachments/assets/7d1437b3-f206-4289-b228-ae6540c99ebd" />

---

## 4. Write a PL/SQL Function to Return the Reverse of a Number

### Steps:
- Create a function named `reverse_number`.
- Accept an input number as parameter.
- Use a loop to reverse the digits of the number.
- Return the reversed number.
- Call the function and display the output.

**Expected Output:**  
Reversed number of 1234 is 4321
<img width="692" height="468" alt="image" src="https://github.com/user-attachments/assets/93d4600b-59d0-4d16-8856-2d8e64ce8548" />
<img width="340" height="123" alt="image" src="https://github.com/user-attachments/assets/78ba3531-9d92-4624-a32e-2f8ec1c5baf4" />

---

## 5. Write a PL/SQL Procedure to Display the Multiplication Table of a Number

### Steps:
- Create a procedure named `print_table`.
- Accept an input number.
- Use a loop from 1 to 10 to multiply the input number.
- Display the multiplication results using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
Multiplication table of 5:  
5 x 1 = 5  
5 x 2 = 10  
5 x 3 = 15  
...  
5 x 10 = 50
<img width="682" height="265" alt="image" src="https://github.com/user-attachments/assets/4bcdaa90-97df-404e-8e7b-2e11e019ba41" />
<img width="436" height="322" alt="image" src="https://github.com/user-attachments/assets/d6e65df0-af9b-4d30-8b2b-b7e87cbaa67a" />

## RESULT
Thus, the PL/SQL programs using procedures and functions were written, compiled, and executed successfully.
