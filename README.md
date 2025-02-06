# Aggregation-Functions
Using aggregation functions for Employee and Department Tables

COUNT()
1. Count the number of employees in each department:
SELECT d.department_name, COUNT(e.Employee_id) AS employee_count
FROM Department d
LEFT JOIN Employee e ON d.department_id = e.department_id
GROUP BY d.department_name;


2. Count the total number of employees:
SELECT COUNT(*) AS total_employees
FROM Employee;



SUM()

3. Get the total salary expenditure for each department:
SELECT d.department_name, SUM(e.salary) AS total_salary
FROM Employee e
JOIN Department d ON e.department_id = d.department_id
GROUP BY d.department_name;


4. Calculate the total salary of all employees:
SELECT SUM(salary) AS total_salary
FROM Employee;


AVG()

5. Find the average salary of employees in each department:
SELECT d.department_name, AVG(e.salary) AS average_salary
FROM Employee e
JOIN Department d ON e.department_id = d.department_id
GROUP BY d.department_name;


6. Find the average salary of all employees:
SELECT AVG(salary) AS average_salary
FROM Employee;


MIN()

7. Find the lowest salary in each department:
SELECT d.department_name, MIN(e.salary) AS lowest_salary
FROM Employee e
JOIN Department d ON e.department_id = d.department_id
GROUP BY d.department_name;


8. Find the lowest salary across all employees:
SELECT MIN(salary) AS lowest_salary
FROM Employee;


MAX()

9.  Find the highest salary in each department:
SELECT d.department_name, MAX(e.salary) AS highest_salary
FROM Employee e
JOIN Department d ON e.department_id = d.department_id
GROUP BY d.department_name;


10.  Find the highest salary across all employees:
SELECT MAX(salary) AS highest_salary
FROM Employee;


---Using Multiple Aggregate Functions in One Query:
Calculate the total, average, minimum, and maximum salary for each department:
SELECT 
    d.department_name,
    SUM(e.salary) AS total_salary,
    AVG(e.salary) AS average_salary,
    MIN(e.salary) AS lowest_salary,
    MAX(e.salary) AS highest_salary
FROM Employee e
JOIN Department d ON e.department_id = d.department_id
GROUP BY d.department_name;

