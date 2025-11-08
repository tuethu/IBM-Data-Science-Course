# Summary: Basic SQL

Congratulations! You have completed this lesson. At this point in the course, you know: 

- The Data Manipulation Language (DML) statements read and modify data. 

- The search condition of the WHERE clause uses a predicate to refine the search.

- The SQL retrieves specific data from databases.

- The COUNT, DISTINCT, and LIMIT are expressions used with SELECT statements. 

   - 1. COUNT

```
SELECT * FROM FilmLocations;
SELECT COUNT(*) FROM FilmLocations;
SELECT COUNT(Locations) FROM FilmLocations WHERE Writer="James Cameron";
SELECT Count(*) FROM FilmLocations WHERE ReleaseYear<1950; #Retrieve the number of rows having a release year older than 1950 from the "FilmLocations" table.
```
   - 2. DISTINCT 

```
SELECT DISTINCT Title FROM FilmLocations;
```
   
   - 3. LIMIT 
  
```
SELECT * FROM FilmLocations LIMIT 25;
SELECT * FROM FilmLocations LIMIT 15 OFFSET 10; #retrieve 15 rows from the table starting from row 11.
```

- The real-world applications of SELECT statements.

 - The INSERT, UPDATE, and DELETE are DML statements for populating and changing tables.
 - 1. INSERT
```
INSERT INTO Instructor(ins_id, lastname, firstname, city, country)
VALUES(4, 'Saha', 'Sandip', 'Edmonton', 'CA'), (5, 'Doe', 'Jane', 'Dhaka', 'BD');
```

 - 2. UPDATE
```
UPDATE Instructor 
SET city='Toronto' 
WHERE firstname="Sandip";
```

 - 3. DELETE
```
DELETE FROM instructor
WHERE firstname = 'Hima';
```


[SQL Cheat Sheet: Basics](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTURldmVsb3BlclNraWxsc05ldHdvcmstREIwMjAxRU4tU2tpbGxzTmV0d29yay9sYWJzL0NoZWF0U2hlZXQvU1FMLUNoZWF0LVNoZWV0LUJhc2Npcy5tZD90PTE3NDYxMTkwNzciLCJ0b29sX3R5cGUiOiJpbnN0cnVjdGlvbmFsLWxhYiIsImF0bGFzX2ZpbGVfaWQiOjEyMzY2LCJhZG1pbiI6ZmFsc2UsImlhdCI6MTc1NzQ0ODM4Nn0.t7w7XLUY7jExmrnfEwG3bUtxwCfWF2htDMaJ7nDqx4Q)

[SELECT statement examples](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTURldmVsb3BlclNraWxsc05ldHdvcmstREIwMjAxRU4tU2tpbGxzTmV0d29yay9sYWJzL3Y4L1NFTEVDVF9zdGF0ZW1lbnRfZXhhbXBsZXMubWQ_dD0xNzQ3OTIwMDg5IiwidG9vbF90eXBlIjoiaW5zdHJ1Y3Rpb25hbC1sYWIiLCJhdGxhc19maWxlX2lkIjozMjA2OCwiYWRtaW4iOmZhbHNlLCJpYXQiOjE3NTc2OTQ0MjJ9.oRclyQyHfuKyxrBRdLY-Q_9Zj8vr8Q7WoDZtmQe_OmU)
