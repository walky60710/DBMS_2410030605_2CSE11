Assignment-Question-3
# EXPERIMENT 03 – ADVANCED RETRIEVAL QUERIES

**Date:** [Insert Date – e.g. 06/02/2026]  
**AIM:** To perform advanced SELECT queries including sorting (ORDER BY), pattern matching (LIKE), multiple conditions (IN, OR, NOT), range filtering (BETWEEN), and calculated fields on employee_master table using MySQL shell.

**Database:** 2410030605_db (or your assigned database name)  
**Table:** employee_master  
**Columns:** emp_id, emp_name, job, dept_no, sal, hiredate

**Note:**  
- All queries are executed in the MySQL shell (black Terminal screen)  
- Screenshots show full command + output for each question  
- Add test rows if needed for better visible results (e.g. low salary for BETWEEN, name starting with M for LIKE 'M%')

## 1. List all employees and jobs in Department 30 in descending order by salary.

**Query:**
```sql
SELECT emp_name, job, sal 
FROM employee_master 
WHERE dept_no = 30 
ORDER BY sal DESC;

``` 
## 2. List job and Department Number of employees whose name are five letters long begin with “A” and end with “N”.
  **Query:**
```sql
SELECT job, dept_no, emp_name 
FROM employee_master 
WHERE LENGTH(emp_name) = 5 
  AND emp_name LIKE 'A%N';
  
Usually Empty set (no matching name like "Arjun", "Aryan" in standard data)
 
``` 
## 3. Display the name of employees whose name start with alphabet S.
  **Query:**
```sql
SELECT emp_name 
FROM employee_master 
WHERE emp_name LIKE 'S%';
  
Names starting with 'S' (e.g. Sneha Verma)
 
``` 
## 4. Display the names of employees whose name ends with alphabet S.
  **Query:**
```sql
SELECT emp_name 
FROM employee_master 
WHERE emp_name LIKE '%S';
  
Usually Empty set (no name ends with 'S' in standard data)
 
``` 
## 5. Display the names of employees working in department number 10 or 20 or 40 or employees working as clerks, salesman or analyst.
  **Query:**
```sql
SELECT emp_name, dept_no, job 
FROM employee_master 
WHERE dept_no IN (10, 20, 40) 
   OR job IN ('CLERK', 'SALESMAN', 'ANALYST');
  
Most employees (dept 10/20 or jobs CLERK/SALESMAN/ANALYST)
 
``` 
## 6. Display employee number and names for employees who earn commission.
Note: No commission column exists → expected error
  **Query:**
```sql
SELECT emp_id, emp_name 
FROM employee_master 
WHERE comm IS NOT NULL;
  
ERROR 1054 (42S22): Unknown column 'comm' in 'where clause'
 
``` 
## 7. Display employee number and total salary for each employee.
  **Query:** (total salary = sal, no commission)
```sql
SELECT emp_id, emp_name, sal AS total_salary 
FROM employee_master;
  
All employees with sal renamed as total_salary
 
``` 
## 8. Display employee number and annual salary for each employee.
  **Query:**
```sql
SELECT emp_id, emp_name, (sal * 12) AS annual_salary 
FROM employee_master;
  
Annual salary = sal × 12 (e.g. 85000.00 → 1020000.00)
 ``` 
## 9. Display the names of all employees working as clerks and drawing a salary more than 3,000.
  **Query:**
```sql
SELECT emp_name, job, sal 
FROM employee_master 
WHERE job = 'CLERK' AND sal > 3000;
  
All CLERKs with sal > 3000 (e.g. Amit Kumar 35000.00, Neha Gupta 32000.00)
 ```
## 10. Display the names of employees who are working as clerk, salesman or analyst and drawing a salary more than 3,000.
  **Query:**
```sql
SELECT emp_name, job, sal 
FROM employee_master 
WHERE job IN ('CLERK', 'SALESMAN', 'ANALYST') 
AND sal > 3000;
