# Summary: Views, Stored Procedures, and Transactions

Congratulations! You have completed this lesson. At this point in the course, you know:

- Views are a dynamic mechanism for presenting data from one or more tables.A transaction represents a complete unit of work, which can be one or more SQL statements.

## 1. Create a View
```
CREATE VIEW EMP_DEPT AS
SELECT EMP_ID, F_NAME, L_NAME, DEP_ID
FROM EMPLOYEES;
```

## 2. Update a View

Modify “EMP_DEPT” such that it displays Department names instead of Department IDs. 
For this, we need to combine information from EMPLOYEES and DEPARTMENTS as follows.
EMP_ID, FNAME, LNAME from EMPLOYEES table and
DEP_NAME from DEPARTMENTS table, combined over the columns DEP_ID and DEPT_ID_DEP

```
CREATE OR REPLACE VIEW EMP_DEPT AS
SELECT EMP_ID, F_NAME, L_NAME, DEP_NAME
FROM EMPLOYEES, DEPARTMENTS
WHERE EMPLOYEES.DEP_ID = DEPARTMENTS.DEPT_ID_DEP;
```

## 3. Drop a View

```
DROP VIEW EMP_DEPT
```

- An ACID transaction (Atomicity, Consistency, Isolation, and Durability) is one where all the SQL statements must complete successfully, or none at all.
![ACID transaction](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%206_Databases%20and%20SQL%20for%20Data%20Science%20with%20Python/Module%206_Bonus%20Module%3A%20Advanced%20SQL%20for%20Data%20Engineers/Lesson%201_Views%2C%20Stored%20Procedures%20and%20Transactions/ACID%20Transaction.png)

- A stored procedure is a set of SQL statements that are stored and executed on the database server, allowing you to send one statement as an alternative to sending multiple statements.

- You can write stored procedures in many different languages like SQL PL, PL/SQL, Java, and C.
