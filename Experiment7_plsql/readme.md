# Experiment 7: PL/SQL – Variables, Control Structures and Loops

## AIM
To write and execute simple PL/SQL programs using variables, loops, and conditional statements.


## THEORY

PL/SQL, which stands for Procedural Language extensions to the Structured Query Language (SQL). It is a combination of SQL along with the procedural features of programming languages.

**Syntax:**
```sql
DECLARE 
   <declarations section> 
BEGIN 
   <executable command(s)>
EXCEPTION 
   <exception handling> 
END;
```

### Basic Components of PL/SQL Block:
- DECLARE: Section to declare variables and constants.
- BEGIN: The execution section that contains PL/SQL statements.
- EXCEPTION: Handles errors or exceptions that occur in the program.
- END: Marks the end of the PL/SQL block.

# PL/SQL Programs – Steps and Expected Output

## 1. Write a PL/SQL program to find the Greatest of Two Numbers

### Steps:
- Declare two numeric variables and initialize them.
- Use an `IF` statement to compare the values.
- Display the greater number using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
Greater number is: 80
## PROGRAM
<img width="832" height="247" alt="image" src="https://github.com/user-attachments/assets/a65512bb-9e54-4a29-9eaa-e37dfde6d89d" />
## OUTPUT
<img width="645" height="267" alt="image" src="https://github.com/user-attachments/assets/78587018-ba89-440e-bf01-b59b459724e3" />

---

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
Sum of first 10 natural numbers is: 55
## PROGRAM
<img width="826" height="331" alt="image" src="https://github.com/user-attachments/assets/a61e9b50-e384-4240-82fb-d1f04c5dfcc6" />
## OUTPUT
<img width="572" height="262" alt="image" src="https://github.com/user-attachments/assets/9c004f47-20e8-4719-97a8-a5637a8c1452" />

---

## 3. Write a PL/SQL program to generate Fibonacci series

### Steps:
- Declare the variable `n` to indicate how many terms to generate.
- Initialize the first two Fibonacci numbers (0 and 1).
- Use a loop to generate the next terms using the formula `c = a + b`.
- Print each term in the series.

**Expected Output:**  
n = 7  
Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8
## PROGRAM
<img width="716" height="470" alt="image" src="https://github.com/user-attachments/assets/c41d73e7-eb11-49ad-a3d9-cdce5fb777db" />
## OUTPUT
<img width="562" height="421" alt="image" src="https://github.com/user-attachments/assets/563a514a-9c04-4a7c-add0-014f7a5ff1bf" />

---

## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.

**Expected Output:**  
n = 1535  
Reversed number is 5351
## PROGRAM
<img width="680" height="330" alt="image" src="https://github.com/user-attachments/assets/f2b9a2d3-01ec-4353-9e98-2bdec6036ad9" />
## OUTPUT
<img width="598" height="281" alt="image" src="https://github.com/user-attachments/assets/c49581f6-9f2f-4465-a143-1d8d60bc628d" />

---

## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.

**Expected Output:**  
a = 10, b = 9, c = 15  
Largest of three number is 15
## PROGRAM
<img width="808" height="427" alt="image" src="https://github.com/user-attachments/assets/af54afdb-89db-4ef1-938b-e9fe53ec849d" />
## OUTPUT
<img width="548" height="251" alt="image" src="https://github.com/user-attachments/assets/992d6f40-d93f-42a1-8a57-0b20ad799501" />

## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.
