# Summary: JOIN Statements

Congratulations! You have completed this lesson. At this point in the course, you know:

- A join combines the rows from two or more tables based on a relationship between certain columns in these tables.

- To combine data from three or more different tables, you simply add new joins to the SQL statement. 

- There are two types of joins: inner join and outer join; and three types of outer joins: left outer join, right outer join, and full outer join.

## 1. INNER JOIN

Retrieve the names and job start dates of all employees who work for department number 5.

```
select E.F_NAME,E.L_NAME, JH.START_DATE, J.JOB_TITLE 
from EMPLOYEES as E 
INNER JOIN JOB_HISTORY as JH on E.EMP_ID=JH.EMPL_ID 
INNER JOIN JOBS as J on E.JOB_ID=J.JOB_IDENT
where E.DEP_ID ='5';
```

## 2. LEFT/RIGHT JOIN

Retrieve employee ID, last name, department ID, and department name for all employees.
```
SELECT E.EMP_ID, E.L_NAME, E.DEP_ID, D.DEP_NAME
FROM EMPLOYEES AS E
LEFT OUTER JOIN DEPARTMENTS AS D
ON E.DEP_ID = D.DEPT_ID_DEP
AND YEAR(E.B_DATE) < 1980;
```

## 3. FULL OUTTER JOIN 

Retrieve the First name, Last name, and Department name of all employees.

```
SELECT E.F_NAME, E.L_NAME, D.DEPT_ID_DEP, D.DEP_NAME
FROM EMPLOYEES AS E
LEFT OUTER JOIN DEPARTMENTS AS D
ON E.DEP_ID=D.DEPT_ID_DEP AND E.SEX = 'M'

UNION

SELECT E.F_NAME, E.L_NAME, D.DEPT_ID_DEP, D.DEP_NAME
from EMPLOYEES AS E
RIGHT OUTER JOIN DEPARTMENTS AS D
ON E.DEP_ID=D.DEPT_ID_DEP AND E.SEX = 'M';
```


- The most common type of join is the inner join, which matches the results from two tables and returns the selected elements from each table, only where corresponding elements in both the tables are the same.

- You can use an alias as shorthand for a table or column name.
