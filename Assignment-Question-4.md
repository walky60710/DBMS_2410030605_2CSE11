# PRACTICAL FILE ASSIGNMENT QUESTION 4

**Date:** 06/02/2026  
**AIM:** To perform date-based filtering, string pattern matching (second letter), aggregate functions, calculated fields, UPDATE increment, and salary condition queries on employee_master table using MySQL shell.

**Database:** 2410030605_db (or your assigned name)  
**Table:** employee_master (columns: emp_id, emp_name, job, dept_no, sal, hiredate)

**Note:**  
- All dates are in 'YYYY-MM-DD' format  
- Jobs are uppercase ('CLERK', 'SALESMAN', 'ANALYST', 'MANAGER')  
- No commission column – questions referring to commission are adapted  
- Add test rows if needed for some conditions

## 1. Display the list of employees who have joined the company before 30th June 80 or after 31st Dec 81.

**Query:**
```sql
SELECT emp_name, hiredate 
FROM employee_master 
WHERE hiredate < '1980-06-30' OR hiredate > '1981-12-31';

```
## 2. Display the names of employees whose names have second alphabet A in their names.

**Query:**
```sql
SELECT emp_name 
FROM employee_master 
WHERE emp_name LIKE '_A%';

```
## 3. Display the names of employees whose name is exactly five characters in length.

**Query:**
```sql
SELECT emp_name 
FROM employee_master 
WHERE LENGTH(emp_name) = 5;

```
## 4. Display the names of employees whose names have second alphabet A in their names.
**Query:**
```SQL
SELECT emp_name 
FROM employee_master 
WHERE emp_name LIKE '_A%';

```
## 5. Display the names of employees who are not working as salesman or clerk or analyst.
**Query:**

```SQL
SELECT emp_name, job 
FROM employee_master 
WHERE job NOT IN ('SALESMAN', 'CLERK', 'ANALYST');

```
## 6. Display the name of the employee along with their annual salary (sal*12). The name of the employee earning highest salary should appear first.
**Query:**

```SQL
SELECT emp_name, (sal * 12) AS annual_salary 
FROM employee_master 
ORDER BY sal DESC;

```
## 7. Display name, sal, hra, pf, da, totalsal for each employee. The output should be in the order of total sal, hra 15% of sal, da 10% of sal, pf 5% of sal. Total salary will be (salhrada)-pf.
**Query:**
```SQL
SELECT 
    emp_name,
    sal,
    ROUND(sal * 0.15, 2) AS hra,
    ROUND(sal * 0.05, 2) AS pf,
    ROUND(sal * 0.10, 2) AS da,
    ROUND((sal + (sal * 0.15) + (sal * 0.10)) - (sal * 0.05), 2) AS totalsal
FROM employee_master;
```
## 8. Update the salary of each employee by 10% increment who are not eligible for commission.
**Query (adapted – update all since no commission column):**
```SQL
UPDATE employee_master SET sal = sal * 1.10;

```
## 9. Display those employees whose salary is more than 3000 after giving 20% increment.
**Query:**
```SQL
SELECT emp_name, sal, ROUND(sal * 1.20, 2) AS salary_after_20pct 
FROM employee_master 
WHERE ROUND(sal * 1.20, 2) > 3000;

```
## 10. Display those employees whose salary contains atleast 3 digits.
**Query:**
```SQL
SELECT emp_name, sal 
FROM employee_master 
WHERE LENGTH(FLOOR(sal)) >= 3;