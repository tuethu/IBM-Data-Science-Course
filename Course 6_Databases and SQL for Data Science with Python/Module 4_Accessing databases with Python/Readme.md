# Summary: Accessing databases using Python

Congratulations! You have completed this lesson. At this point in the course, you know: 

- Magic commands are special commands that provide special functionalities.

- Cell magics are commands prefixed with two %% characters and operate on multiple input lines. The syntax for connecting to magic sql using sqllite is
```
%sql sqlite://DatabaseName
```
- DB APIs are commands prefixed with two %% characters and operate on multiple input lines.

- The two main concepts in the Python DB API are Connection Objects and Query Objects.

- A database cursor is a control structure that enables traversal over the records in a database. 

- Pandas’ methods are equipped with common mathematical and statistical methods.  

- The pandas.read_csv() function is used to read the database CSV file.

- The sqlite3.connect() function is used to connect to a database.

- To use pandas to retrieve data from the database tables, load data using the read_sql method and select the SQL Select Query

- A categorical scatterplot is created using the swarmplot() method by the <ins>seaborn</ins> package.
```
!pip install matplotlib seaborn
income_and_hardship = %sql SELECT per_capita_income_, hardship_index FROM chicago_socioeconomic_data;
plot = sns.jointplot(x='per_capita_income_',y='hardship_index', data=income_and_hardship.DataFrame())
```


- Cell magic in Jupyter Notebooks can be used as:
 1. Timing a complete cell block as per requirement(%%timeit) (Run the cell multiple times and give average execution time)

```
%%timeit
squares = [x**2 for x in range(1000)]

#Output: 1000 loops, best of 5: 250 µs per loop
```

   2. Coding in Jupyter notebook using a programming language other than Python 

```
%%bash
echo "Hello from Bash!"
ls -l
```

- 2 correct ways to query a database table using python
```
out = pd.read_sql("SELECT * FROM Employees", conn)
#out = pandas.read_sql(query_statement, connection_object)
```
or 
```
cursor = connection.execute("SELECT * FROM Employees")
out = cursor.fetchall()
#cursor = connection.execute(query_statement)
```


- The csv file is read and converted into an SQL table 'Employees' under the HR database in the following codes

```
import sqlite3

import pandas as pd

conn = sqlite3.connect(‘HR.db’)

data = pd.read_csv(‘./employees.csv’)

data.to_sql(‘Employees’, conn)
```


## Step-by-Step: Querying a MySQL Table in Python
import mysql.connector

### Step 1: Connect to the database
conn = mysql.connector.connect(
    host="localhost",
    user="your_username",
    password="your_password",
    database="your_database"
)

### Step 2: Create a cursor object
cursor = conn.cursor()

### Step 3: Write and execute your query
query = "SELECT * FROM Employees;"
cursor.execute(query)

### Step 4: Fetch results
results = cursor.fetchall()
for row in results:
    print(row)

### Step 5: Close the connection
cursor.close()
conn.close()

[SQL Cheat Sheet: Accessing Databases using Python](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTURldmVsb3BlclNraWxsc05ldHdvcmstREIwMjAxRU4tU2tpbGxzTmV0d29yay9sYWJzL3Y4L0NoZWF0X3NoZWV0X0FjY2Vzc19kYl9weXRob24ubWQ_dD0xNzQ2MTIyNTk5IiwidG9vbF90eXBlIjoiaW5zdHJ1Y3Rpb25hbC1sYWIiLCJhdGxhc19maWxlX2lkIjozMjExNywiYWRtaW4iOmZhbHNlLCJpYXQiOjE3NTc2OTQ0MjN9.ZtFqOMseyPCrZ1S21ESt4-ZrSRe0CdEUOozRMEkLUjo)


