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