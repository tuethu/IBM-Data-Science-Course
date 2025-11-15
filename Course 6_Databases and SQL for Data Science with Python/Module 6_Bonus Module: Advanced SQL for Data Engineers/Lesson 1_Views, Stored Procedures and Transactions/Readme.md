# Summary: Views, Stored Procedures, and Transactions

Congratulations! You have completed this lesson. At this point in the course, you know:

- Views are a dynamic mechanism for presenting data from one or more tables.A transaction represents a complete unit of work, which can be one or more SQL statements.
## VIEW

### 1. Create a View
```
CREATE VIEW EMP_DEPT AS
SELECT EMP_ID, F_NAME, L_NAME, DEP_ID
FROM EMPLOYEES;
```

### 2. Update a View

Modify “EMP_DEPT” such that it displays Department names instead of Department IDs.\ 
For this, we need to combine information from EMPLOYEES and DEPARTMENTS as follows.\
EMP_ID, FNAME, LNAME from EMPLOYEES table and\
DEP_NAME from DEPARTMENTS table, combined over the columns DEP_ID and DEPT_ID_DEP

```
CREATE OR REPLACE VIEW EMP_DEPT AS
SELECT EMP_ID, F_NAME, L_NAME, DEP_NAME
FROM EMPLOYEES, DEPARTMENTS
WHERE EMPLOYEES.DEP_ID = DEPARTMENTS.DEPT_ID_DEP;
```

### 3. Drop a View

```
DROP VIEW EMP_DEPT
```

- An ACID transaction (Atomicity, Consistency, Isolation, and Durability) is one where all the SQL statements must complete successfully, or none at all.
![ACID transaction](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%206_Databases%20and%20SQL%20for%20Data%20Science%20with%20Python/Module%206_Bonus%20Module%3A%20Advanced%20SQL%20for%20Data%20Engineers/Lesson%201_Views%2C%20Stored%20Procedures%20and%20Transactions/ACID%20Transaction.png)


## STORED PROCEDURE

- A stored procedure is a set of SQL statements that are stored and executed on the database server, allowing you to send one statement as an alternative to sending multiple statements.

- You can write stored procedures in many different languages like SQL PL, PL/SQL, Java, and C.

### 1. Create a stored procedure routine named UPDATE_SALEPRICE

This procedure routine will take animal ID and health conditon as parameters which will be used to update the sale price of animal in the PETSALE table by an amount depending on their health condition. Suppose that:\

For animal with ID XX having BAD health condition, the sale price will be reduced further by 25%.\
For animal with ID YY having WORSE health condition, the sale price will be reduced further by 50%.\
For animal with ID ZZ having other health condition, the sale price won't change.\

```
DELIMITER @
CREATE PROCEDURE UPDATE_SALEPRICE (IN Animal_ID INTEGER, IN Animal_Health VARCHAR(5))
BEGIN
    IF Animal_Health = 'BAD' THEN
        UPDATE PETSALE
        SET SALEPRICE = SALEPRICE - (SALEPRICE * 0.25)
        WHERE ID = Animal_ID;
    ELSEIF Animal_Health = 'WORSE' THEN
        UPDATE PETSALE
        SET SALEPRICE = SALEPRICE - (SALEPRICE * 0.5)
        WHERE ID = Animal_ID;
    ELSE
        UPDATE PETSALE
        SET SALEPRICE = SALEPRICE
        WHERE ID = Animal_ID;
    END IF;
END @

DELIMITER ;
```

### 2. Call the UPDATE_SALEPRICE routine 

```
   CALL RETRIEVE_ALL;

   CALL UPDATE_SALEPRICE(3, 'WORSE');

   CALL RETRIEVE_ALL;
```

### 3. Drop the stored procedure routine

```
DROP PROCEDURE UPDATE_SALEPRICE;

CALL UPDATE_SALEPRICE;
```


