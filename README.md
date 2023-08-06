# SQL-Lab2

# We will use the Employees and Awards table below:

 <img src="Lab2.png" width="500" height="500">

### Q1: Choose all employees who have received an award (Nested Query)?
Query: SELECT * FROM employee WHERE id IN (SELECT employee_id From Awards );

Output: <img src="SQL14.png">
 

### Q2: Choose all employees who have never received an award (Nested Query)?
Query: SELECT * FROM employee WHERE id NOT IN (SELECT employee_id From Awards );

Output: <img src="SQL15.png" >

 
### Q3: Choose all Developers who make more than all Managers combined (Nested Query)?
Query: SELECT * FROM employee WHERE role = "Developer" and salary > (SELECT MAX(salary) From employee WHERE role = "Manager" );

Output: <img src="SQL16.png">

 
### Q4: Choose all Developers who make more money than any Manager (Nested Query)?
Query: SELECT * FROM employee WHERE role = "Developer" and salary > (SELECT salary From employee WHERE role = "Manager" );

Output: <img src="SQL17.png">

 
### Q5: Choose all employees whose salaries are higher than the average for their position. (Nested Query)?
Query: SELECT * FROM employee WHERE salary > (SELECT AVG(salary) From employee GROUP BY "role");

Output: <img src="SQL18.png">
