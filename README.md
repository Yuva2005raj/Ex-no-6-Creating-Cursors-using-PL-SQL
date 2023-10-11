# Ex. No: 6 Creating Cursors using PL/SQL

### AIM: To create a cursor using PL/SQL.

### Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create a cursor named as employee_cursor
3. Using cursor read each record and display the result
4. Close the cursor

### Program:
### Create employee table
```sql
CREATE TABLE employee(empid NUMBER,
 empname VARCHAR(10),
dept VARCHAR(10),
salary NUMBER);
```
### PL/SQL Cursor code
```sql
SET SERVEROUTPUT ON;
DECLARE
CURSOR employee_cursor IS
SELECT * FROM employee;
emp_id NUMBER;
emp_name VARCHAR2(20);
emp_dept VARCHAR2(20);
emp_salary NUMBER;
BEGIN
OPEN employee_cursor;
LOOP
FETCH employee_cursor INTO emp_id, emp_name, emp_dept, emp_salary;
EXIT WHEN employee_cursor%NOTFOUND;
 
DBMS_OUTPUT.PUT_LINE('Employee ID: ' || emp_id);
DBMS_OUTPUT.PUT_LINE('Employee Name: ' || emp_name);
DBMS_OUTPUT.PUT_LINE('Department: ' || emp_dept);
DBMS_OUTPUT.PUT_LINE('Salary: ' || emp_salary);
DBMS_OUTPUT.PUT_LINE('--------------------------');
END LOOP;
CLOSE employee_cursor;
END;
/
```
### Output:
![image](https://github.com/Prajeeth17/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/120513885/a1e0eb46-e3b2-48ad-97fe-a81208e28aa6)

### Result:
A cursor has been created successfully using PL/SQL
