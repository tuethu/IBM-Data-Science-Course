
# Summary: Functions, Multiple Tables, and Sub-queries

Congratulations! You have completed this lesson. At this point in the course, you know: 

- Tools for database management that offer built-in functions for performing operations on data within the database itself.

- That when working with large datasets, you may save time by using built-in functions rather than first retrieving the data into your application and then executing functions on the retrieved data.

- You can use sub-queries to form more powerful queries than otherwise.

- You can use a sub-select expression to evaluate some built-in aggregate functions like the average function. 

- Derived tables or table expressions are sub-queries where the outer query uses the results of the sub-query as a data source.

## 1. Aggregation Functions
```
SELECT SUM(COST) FROM PETRESCUE;

SELECT MAX(QUANTITY) FROM PETRESCUE;

SELECT AVG(COST) FROM PETRESCUE;
```

- Display the average cost of rescuing a single dog
```
SELECT AVG(COST/QUANTITY) FROM PETRESCUE WHERE ANIMAL = 'Dog';
```

##  2. Scalar Functions and String Functions

```
SELECT ROUND(COST) FROM PETRESCUE;
or
SELECT ROUND(COST, 0) FROM PETRESCUE;
```

- Round the value to 2 decimal places
```
SELECT ROUND(COST, 2) FROM PETRESCUE;
```

- Display the animal name in each rescue in uppercase without duplication
```
SELECT DISTINCT UCASE(ANIMAL) FROM PETRESCUE;
```

- Display all the columns from the PETRESCUE table where the animal(s) rescued are cats. Use cat in lowercase in the query
```
SELECT * FROM PETRESCUE WHERE LCASE(ANIMAL)="cat";
```


##  3. Date Functions

- Display the number of rescues in the 5th month.
```
SELECT SUM(QUANTITY) FROM PETRESCUE WHERE MONTH(RESCUEDATE)="05";
```

- The rescue shelter is supposed to find good homes for all animals within 1 year of their rescue. Write a query that displays the ID and the target date
```
SELECT ID, DATE_ADD(RESCUEDATE, INTERVAL 1 YEAR) FROM PETRESCUE;
```


SELECT DAY(RESCUEDATE) FROM PETRESCUE;
SELECT DATE_SUB(RESCUEDATE, INTERVAL 3 DAY) FROM PETRESCUE

SELECT FROM_DAYS(DATEDIFF(CURRENT_DATE, RESCUEDATE)) FROM PETRESCUE
To present the output in a YYYY-MM-DD format


##  4. Accessing multiple tables with <ins>sub-queries</ins>

- Retrieve JOB information and a list of employees whose birth year is after 1976

```
SELECT JOB_TITLE, MIN_SALARY, MAX_SALARY, JOB_IDENT
FROM JOBS
WHERE JOB_IDENT IN (SELECT JOB_ID
                    FROM EMPLOYEES
                    WHERE YEAR(B_DATE)>1976 );
```

##  5. Accessing multiple tables with <ins>Implicit Joins</ins>

- Retrieve JOB information and a list of employees whose birth year is after 1976

```
SELECT J.JOB_TITLE, J.MIN_SALARY, J.MAX_SALARY, J.JOB_IDENT
FROM JOBS J, EMPLOYEES E
WHERE E.JOB_ID = J.JOB_IDENT AND YEAR(E.B_DATE)>1976;
```

SELECT EMP_ID,F_NAME,L_NAME, JOB_TITLE
FROM EMPLOYEES E, JOBS J
WHERE E.JOB_ID = J.JOB_IDENT;
or
SELECT E.EMP_ID, E.F_NAME, E.L_NAME, J.JOB_TITLE
FROM EMPLOYEES E, JOBS J
WHERE E.JOB_ID = J.JOB_IDENT;




[SQL Cheat Sheet: FUNCTIONS and Implicit JOIN](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTURldmVsb3BlclNraWxsc05ldHdvcmstREIwMjAxRU4tU2tpbGxzTmV0d29yay9sYWJzL3Y4L2NoZWF0c2hlZXRfZnVuY3Rpb25zLm1kP3Q9MTc0NjEyMjU1MCIsInRvb2xfdHlwZSI6Imluc3RydWN0aW9uYWwtbGFiIiwiYXRsYXNfZmlsZV9pZCI6MzIwOTgsImFkbWluIjpmYWxzZSwiaWF0IjoxNzU3Njk0NDIzfQ.I1SG2BwwJGLDa6qRFJmpYWhXZOIMacRliipnNZzydfY)

