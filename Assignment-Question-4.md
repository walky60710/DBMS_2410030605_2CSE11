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