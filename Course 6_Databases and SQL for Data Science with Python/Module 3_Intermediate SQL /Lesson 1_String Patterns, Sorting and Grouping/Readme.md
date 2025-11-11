# Summary: Refining Your Results

Congratulations! You have completed this lesson. At this point in the course, you know: 

- You can use the WHERE clause to refine your query results. 

- The search condition of the WHERE clause uses a predicate to refine the search. 

- You can use the wildcard character (%) as a substitute for unknown characters in a pattern. 

- You can use BETWEEN ... AND ... to specify a range of numbers. 

- You can sort query results into ascending or descending order, using the ORDER BY clause to specify the column to sort on. 

- You can group query results by using the GROUP BY clause.


## 1. String Patterns
- Rretrieve the first names F_NAME and last names L_NAME of all employees who live in Elgin, IL
  
```
SELECT F_NAME, L_NAME
FROM EMPLOYEES
WHERE ADDRESS LIKE '%Elgin,IL%';
```

- Identify the employees who were born during the 70s

```
SELECT F_NAME, L_NAME
FROM EMPLOYEES
WHERE B_DATE LIKE '197%';
```

## 2. Sorting

```
SELECT F_NAME, L_NAME, DEP_ID 
FROM EMPLOYEES
ORDER BY DEP_ID;
```

## 3. Grouping
- Limit the result to departments with fewer than 4 employees,

```
SELECT DEP_ID, AVG(SALARY)
FROM EMPLOYEES
GROUP BY DEP_ID
HAVING AVG(SALARY) >= 60000
ORDER BY AVG(SALARY) DESC;
```


[SQL Cheat Sheet: Intermediate - LIKE, ORDER BY, GROUP BY](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTURldmVsb3BlclNraWxsc05ldHdvcmstREIwMjAxRU4tU2tpbGxzTmV0d29yay9sYWJzL3Y4L0NoZWF0U2hlZXRfTGlrZV9PcmRlckJ5X0dyb3VwQnkubWQ_dD0xNzQ4NTQ1Njg0IiwidG9vbF90eXBlIjoiaW5zdHJ1Y3Rpb25hbC1sYWIiLCJhdGxhc19maWxlX2lkIjozMjA5NiwiYWRtaW4iOmZhbHNlLCJpYXQiOjE3NTc2OTQ0MjN9.bjUno_8e2qOCIYKbPb628WKcRrvRozK1W4hI-a8CNYg)
