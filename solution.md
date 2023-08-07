# SQL-LAB2

**Q1:** Choose all employees who have received an award (Nested Query)?
```SQL
 SELECT * FROM employee WHERE id IN (SELECT employee_id FROM awards);
```

**Q2:** Choose all employees who have never received an award (Nested Query)?
```SQL
SELECT * FROM employee WHERE id NOT IN (SELECT employee_id FROM awards);
```

**Q3:**Choose all Developers who make more than all Managers combined (Nested Query)?
```SQL
SELECT * FROM employee WHERE role = "Developer" AND salary > (SELECT SUM(salary) FROM employee WHERE role = "Manager")
```

**Q4:** Choose all Developers who make more money than any Manager (Nested Query)?
```SQL
SELECT * FROM employee WHERE role = "Developer" AND salary > (SELECT min(salary) FROM employee WHERE role = "Manager")

```

**Q5** Choose all employees whose salaries are higher than the average for their position. (Nested Query)?
```SQL
SELECT name, salary, role FROM employee as ex WHERE salary > 
(select avg(salary) from employee where role = ex.role);
```
