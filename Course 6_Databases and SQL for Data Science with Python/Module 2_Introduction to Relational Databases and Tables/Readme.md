# Summary: Relational Database Concepts and Tables

Congratulations! You have completed this lesson. At this point in the course, you know:  

- A database is a repository of data that provides functionality for adding, modifying, and querying the data.  

- SQL is a language used to query or retrieve data from a relational database.  

- The Relational Model is the most used data model for databases because it allows for data independence.  

- The primary key of a relational table uniquely identifies each tuple or row, preventing duplication of data and providing a way of defining relationships between tables.  

- SQL statements fall into two different categories: Data Definition Language (DDL) statements and Data Manipulation Language (DML) statements.
  ![DDL and DML](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%206_Databases%20and%20SQL%20for%20Data%20Science%20with%20Python/Module%202_Introduction%20to%20Relational%20Databases%20and%20Tables/DDL%20and%20DML.jpg)
  
## 1. DDL (Data Definition Language) 
such as CREATE, TRUNCATE (Remove all data but keep the table), DROP (Delete the table), RENAME, ALTER (Add a new column)

 1. CREATE

```
CREATE TABLE PETSALE (
        ID INTEGER NOT NULL,
        PET CHAR(20),
        SALEPRICE DECIMAL(6,2),
        PROFIT DECIMAL(6,2),
        SALEDATE DATE
        );
```

   2. ALTER
      
2.1. Adding a column

```
ALTER TABLE PETSALE
ADD COLUMN QUANTITY INTEGER;
```

   2.2. Modify a column
        
```
ALTER TABLE PETSALE
MODIFY PET VARCHAR(20);
```
  2.3. Deleting a column

```
ALTER TABLE PETSALE
DROP COLUMN PROFIT;
```

   2.4. Rename a Column
- Rename the column PET to ANIMAL of the PETSALE

```
ALTER TABLE `PETSALE` CHANGE `PET` `ANIMAL` varchar(20);
```

   3. TRUNCATE statement (remove all rows from the table)

```
TRUNCATE TABLE PET ;
```

   4. DROP (delete an existing table)
      
```
DROP TABLE PET;
```


## 2. Data Manipulation Language (DML) 
such as INSERT, UPDATE, DELETE, SELECT, MERGE

   1. INSERT
      
```
INSERT INTO PETSALE VALUES
        (1,'Cat',450.09,100.47,'2018-05-29'),
        (2,'Dog',666.66,150.76,'2018-06-01'),
        (3,'Parrot',50.00,8.9,'2018-06-04'),
        (4,'Hamster',60.60,12,'2018-06-11'),
        (5,'Goldfish',48.48,3.5,'2018-06-14');
```
   2. UPDATE
      
```
UPDATE PETSALE SET QUANTITY = 9 WHERE ID = 1;
UPDATE PETSALE SET QUANTITY = 3 WHERE ID = 2;
UPDATE PETSALE SET QUANTITY = 2 WHERE ID = 3;
```

   3. SELECT
```
SELECT * FROM PET;
```


### [Optional] Hands-on Lab Using IBM Db2
[Lab: Create Db2 service instance and Get started with the Db2 console](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTURldmVsb3BlclNraWxsc05ldHdvcmstREIwMjAxRU4tU2tpbGxzTmV0d29yay9sYWJzL0xhYnNfQ291cnNlcmFfVjUvbGFicy9MYWIlMjAtJTIwU2lnbiUyMHVwJTIwZm9yJTIwSUJNJTIwQ2xvdWQlMjAtJTIwQ3JlYXRlJTIwRGIyJTIwc2VydmljZSUyMGluc3RhbmNlJTIwLSUyMEdldCUyMHN0YXJ0ZWQlMjB3aXRoJTIwdGhlJTIwRGIyJTIwY29uc29sZS9pbnN0cnVjdGlvbmFsLWxhYnMubWQ_dD0xNzQ2MTE5MTQzIiwidG9vbF90eXBlIjoiaW5zdHJ1Y3Rpb25hbC1sYWIiLCJhdGxhc19maWxlX2lkIjoxMjM4MCwiYWRtaW4iOmZhbHNlLCJpYXQiOjE3NTc0NDgzOTJ9.PwxJoouoGKLhQsPtlesj6J2DH6g2wJhQKC8eQ0zE1Pw)

[Hands-on Lab: Create Tables using SQL Scripts and Load Data into Tables](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTURldmVsb3BlclNraWxsc05ldHdvcmstREIwMjAxRU4tU2tpbGxzTmV0d29yay9sYWJzL0xhYnNfQ291cnNlcmFfVjUvbGFicy9MYWIlMjAtJTIwQ3JlYXRlJTIwdGFibGVzJTIwdXNpbmclMjBTUUwlMjBzY3JpcHRzJTIwYW5kJTIwTG9hZCUyMGRhdGElMjBpbnRvJTIwdGFibGVzL2luc3RydWN0aW9uYWwtbGFicy5tZD90PTE3NDYxMTkxNzgiLCJ0b29sX3R5cGUiOiJpbnN0cnVjdGlvbmFsLWxhYiIsImF0bGFzX2ZpbGVfaWQiOjEyMzY4LCJhZG1pbiI6ZmFsc2UsImlhdCI6MTc1NzQ0ODM4N30.6nN25MoWC7VynbMPVjoaoLurvtfIIOZPesgcw75Qygs)

[Lab: CREATE, ALTER, TRUNCATE, DROP Tables](https://www.coursera.org/learn/sql-data-science/supplement/3oLXs/optional-hands-on-lab-using-ibm-db2)



[Reading: Examples to ALTER and TRUNCATE tables using MySQL](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTURldmVsb3BlclNraWxsc05ldHdvcmstREIwMjAxRU4tU2tpbGxzTmV0d29yay9sYWJzL3Y4L0FsdGVyX1RydW5jYXRlX3JlYWRpbmcubWQ_dD0xNzQ2MTIyNDk5IiwidG9vbF90eXBlIjoiaW5zdHJ1Y3Rpb25hbC1sYWIiLCJhdGxhc19maWxlX2lkIjozMjA3MCwiYWRtaW4iOmZhbHNlLCJpYXQiOjE3NTc2OTQ0MjJ9.JZMtjW9DRy8N0AffWssTwGh5L6w-0X_8M8ZqHFsjLJg)

[Examples to CREATE and DROP tables](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTURldmVsb3BlclNraWxsc05ldHdvcmstREIwMjAxRU4tU2tpbGxzTmV0d29yay9sYWJzL3Y4L0NyZWF0ZV9Ecm9wX3JlYWRpbmcubWQ_dD0xNzQ3ODI1NDU4IiwidG9vbF90eXBlIjoiaW5zdHJ1Y3Rpb25hbC1sYWIiLCJhdGxhc19maWxlX2lkIjozMjA3NCwiYWRtaW4iOmZhbHNlLCJpYXQiOjE3NTc2OTQ0MjJ9.Fxo-Psgt5k5dtsEXJZVG9NLLMAaETs6cZNILY43wGBQ)

[Reading: Understanding Relational Model Constraints](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0E3aFE5NkI2RGRMSE5sVlVjRGR3bXcvUmVhZGluZy0lMjBVbmRlcnN0YW5kaW5nJTIwUmVsYXRpb25hbCUyME1vZGVsJTIwQ29uc3RyYWludHMtdjEubWQ_dD0xNzU1ODYyNDY0IiwidG9vbF90eXBlIjoiaW5zdHJ1Y3Rpb25hbC1sYWIiLCJhdGxhc19maWxlX2lkIjozMjQ1MTQsImFkbWluIjpmYWxzZSwiaWF0IjoxNzU3Njk3NjQ5fQ.oXis-OKXPkFEbhNft7iShfSEv6jX_l0jRM-x1ldoCv4)

[SQL Scripts - Uses and Applications](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTURldmVsb3BlclNraWxsc05ldHdvcmstREIwMjAxRU4tU2tpbGxzTmV0d29yay9sYWJzL3Y4L3NxbF9zY3JpcHRfcmVhZGluZy5tZD90PTE3NDYxMjI1NTIiLCJ0b29sX3R5cGUiOiJpbnN0cnVjdGlvbmFsLWxhYiIsImF0bGFzX2ZpbGVfaWQiOjMyMTIzLCJhZG1pbiI6ZmFsc2UsImlhdCI6MTc1NzY5NDQyM30.5IjyXufcLj7OCdEPaXNb_4Bv8Bt0U_PCsIbClggtRgg)

[SQL Cheat Sheet: CREATE TABLE, ALTER, DROP, TRUNCATE](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTURldmVsb3BlclNraWxsc05ldHdvcmstREIwMjAxRU4tU2tpbGxzTmV0d29yay9sYWJzL0NoZWF0U2hlZXQvU1FMLUNoZWF0LVNoZWV0LUNyZWF0ZS1UYWJsZS5tZD90PTE3NDYxMTkwODIiLCJ0b29sX3R5cGUiOiJpbnN0cnVjdGlvbmFsLWxhYiIsImF0bGFzX2ZpbGVfaWQiOjEyMzY0LCJhZG1pbiI6ZmFsc2UsImlhdCI6MTc1NzQ0ODM4Nn0.uMe86Dilvfs4aTAN8PNm2MpM1UJKRFCgw84EW6Uotr0)
