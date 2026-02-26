# PRACTICAL FILE ASSIGNMENT QUESTION 5

**Date:** [Insert Date – e.g. 06/02/2026]  
**AIM:** To perform aggregate functions (COUNT, SUM, MAX, MIN, AVG), string case conversions (UPPER, LOWER, proper case), and length functions (LENGTH) on the employee_master table using MySQL command-line shell.

**Database:** 2410030605_db (or your assigned database name)  
**Table:** employee_master  
**Columns:** emp_id, emp_name, job, dept_no, sal, hiredate

**Note:**  
- All queries are executed in the MySQL shell (black Terminal screen)  
- Screenshots show full command + output for each question  
- Add test rows if needed for better visible results

## 1. Display the total number of employees working in the company.

**Query:**
```sql
SELECT COUNT(*) AS total_employees FROM employee_master;

```
## 2. Display the total salary being paid to all employees.
**Query:**
```sql
SELECT SUM(sal) AS total_salary FROM employee_master;

```
## 3. Display the maximum salary from employee table.
**Query:**
```sql
SELECT MAX(sal) AS max_salary FROM employee_master;

```
## 4. Display the minimum salary from employee table.
**Query:**
```sql
SELECT MIN(sal) AS min_salary FROM employee_master;

```
## 5. Display the average salary from employee table.
**Query:**
```sql
SELECT AVG(sal) AS avg_salary FROM employee_master;
```
## 6. Display the maximum salary being paid to clerk.
**Query:**
```sql
SELECT MAX(sal) AS max_clerk_salary FROM employee_master WHERE job = 'CLERK';

```
## 7. Display the maximum salary being paid in dept no 20.
**Query:**
```sql
SELECT MAX(sal) AS max_dept20_salary FROM employee_master WHERE dept_no = 20;

```
## 8. Display the minimum salary paid to any salesman.
**Query:**
```sql
SELECT MIN(sal) AS min_salesman_salary FROM employee_master WHERE job = 'SALESMAN';
```

## 9. Display the average salary drawn by managers.
**Query:**
```sql
SELECT AVG(sal) AS avg_manager_salary FROM employee_master WHERE job = 'MANAGER';

```
## 10. Display the total salary drawn by analyst working in dept no 40.
**Query:**
```sql
SELECT SUM(sal) AS total_analyst_dept40 FROM employee_master 
WHERE job = 'ANALYST' AND dept_no = 40;

```
## 11. Display the names of the employees in Uppercase.
**Query:**
```sql
SELECT UPPER(emp_name) AS upper_name FROM employee_master;

```
## 12. Display the names of the employees in Lowercase.
**Query:**
```sql
SELECT LOWER(emp_name) AS lower_name FROM employee_master;

```
## 13. Display the names of the employees in Proper case.
**Query:** (My```sql has no built-in PROPER/INITCAP – using custom logic)
```sql
SELECT CONCAT(UPPER(LEFT(emp_name, 1)), LOWER(SUBSTRING(emp_name, 2))) AS proper_name 
FROM employee_master;
```
## 14. Display the length of Your name using appropriate function.
**Query:** (replace 'YourNameHere' with your actual name)
```sql
SELECT LENGTH('YourNameHere') AS name_length;
Example (replace with your name):
```sql
SELECT LENGTH('Fahim') AS name_length;
```
## 15. Display the length of all the employee names.
**Query:**
```sql
SELECT emp_name, LENGTH(emp_name) AS name_length FROM employee_master;

