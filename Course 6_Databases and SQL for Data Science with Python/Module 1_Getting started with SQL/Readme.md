# Summary: Basic SQL

Congratulations! You have completed this lesson. At this point in the course, you know: 

- The Data Manipulation Language (DML) statements read and modify data. 

- The search condition of the WHERE clause uses a predicate to refine the search.

- The SQL retrieves specific data from databases.

- The COUNT, DISTINCT, and LIMIT are expressions used with SELECT statements. 
  - COUNT
```
SELECT * FROM FilmLocations;
SELECT COUNT(*) FROM FilmLocations;
SELECT COUNT(Locations) FROM FilmLocations WHERE Writer="James Cameron";
SELECT Count(*) FROM FilmLocations WHERE ReleaseYear<1950; #Retrieve the number of rows having a release year older than 1950 from the "FilmLocations" table.
```
  - DISTINCT
```
SELECT DISTINCT Title FROM FilmLocations;
```
  - LIMIT
```
SELECT * FROM FilmLocations LIMIT 25;
SELECT * FROM FilmLocations LIMIT 15 OFFSET 10; #retrieve 15 rows from the table starting from row 11.
```
- The real-world applications of SELECT statements.

 - The INSERT, UPDATE, and DELETE are DML statements for populating and changing tables.
     - INSERT
```
INSERT INTO Instructor(ins_id, lastname, firstname, city, country)
VALUES(4, 'Saha', 'Sandip', 'Edmonton', 'CA'), (5, 'Doe', 'Jane', 'Dhaka', 'BD');
```
     - UPDATE
```
UPDATE Instructor 
SET city='Toronto' 
WHERE firstname="Sandip";
```
     - DELETE
```
DELETE FROM instructor
WHERE firstname = 'Hima';

```
