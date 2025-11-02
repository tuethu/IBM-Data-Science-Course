# Summary: APIs and Data Collection

Congratulations! You have completed this module. At this point, you know that: 

## Lesson 1_Simple APIs

- Simple APIs in Python are application programming interfaces that provide straightforward and easy-to-use methods for interacting with services, libraries, or data, often with minimal configuration or complexity.

  - An API lets two pieces of software talk to each other.

  - Using an API library in Python entails importing the library, calling its functions or methods to make HTTP requests, and parsing the responses to access data or services provided by the API.

  - Pandas API processes the data by communicating with the other software components.

  - An Instance forms when you create a dictionary and then use the DataFrames constructor to create a Pandas object. 

  - Method “head()” will display the mentioned number of rows from the top (default 5) of DataFrames, while method “mean()” will calculate the mean and return the values
 
```
import pandas as pd
import matplotlib.pyplot as plt

dict_={'a':[11,21,31],'b':[12,22,32]}

df=pd.DataFrame(dict_)
type(df)

df.head()
df.mean()

```
 
[Reading: Some Context on APIs](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTURldmVsb3BlclNraWxsc05ldHdvcmstUFkwMTAxRU4tU2tpbGxzTmV0d29yay9sYWJzL21vZF81L0FQSV9yZWxldmFuY2UubWQ_dD0xNzQ2MTE4NzY1IiwidG9vbF90eXBlIjoiaW5zdHJ1Y3Rpb25hbC1sYWIiLCJhdGxhc19maWxlX2lkIjoxMDg2MSwiYWRtaW4iOmZhbHNlLCJpYXQiOjE3NTc0NDgzMTh9.jOj82UHSpxVpe33QE87i_f2CJwYgWN48DuBZDaxSzQ0)


## Lesson 2_REST APIs

- Rest APIs allow you to communicate through the internet, taking advantage of resources like storage, access more data, AI algorithms, and so on.

  - HTTP methods transmit data over the internet.

  - An HTTP message typically includes a JSON file with instructions for operations.

  - HTTP messages containing JSON files are returned to the client as a response from web services.

  - Dealing with time series data involves using the Pandas time series function. 

  - You can get data for daily candlesticks and plot the chart using Plotly with the candlestick plot. 


## Lesson 2_HTTP Requests 

- The HTTP (HyperText Transfer Protocol) transfers data, including web pages and resources, between a client (a web browser) and a server on the World Wide Web.

  - The HTTP protocol is commonly used for implementing various types of REST APIs.

  - An HTTP response includes information like the type of resource, length of resource, and so on

  - Uniform resource locator (URL) is the most popular way to find resources on the web.

  - URL is divided into three parts: scheme, internet address or base URL, and route
 
    - Scheme:- This is this protocol, for this lab it will always be http://
    - Internet address or Base URL :- This will be used to find the location here are some examples: www.ibm.com and  www.gitlab.com 
    - Route:- Location on the web server for example: /images/IDSNlogo.png

  - The GET method is one of the popular methods of requesting information. Some other methods may also include the body.
```
data2 = requests.get("https://official-joke-api.appspot.com/jokes/ten") #Using requests.get("url") function, load the data from the URL
results2 = json.loads(data2.text) #Retrieve results using json.loads() function
df3 = pd.DataFrame(results2) #Convert json data into pandas data frame. Drop the type and id columns
df3.drop(columns=["type","id"],inplace=True)
df3
```
  - Response method contains the version and body of the response.

  - POST submits data to the server, PUT updates data already on the server, DELETE deletes data from the server
  - 
![HTTP and Requests](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%204_Python%20for%20Data%20Science%20and%20AI/Module%205_APIs%20and%20Data%20Collection/Lesson%202_REST%20APIs%20%26%20HTTP%20Requests/HTTP%20and%20Requests.png)


Requests is a Python library that allows you to send HTTP/1.1 requests easily

  - You can modify the results of your query with the GET method.

```
url_post='http://httpbin.org/post'
r_post=requests.post(url_post,data=payload)
print("POST request body:",r_post.request.body)
print("GET request body:",r.request.body)

#results (We can compare the POST and GET request body, we see only the POST request has a body)
POST request body: name=Joseph&ID=123 #result
GET request body: None #result 
```

  - You can obtain multiple requests from a URL like name, ID, and so on with a Query string.

![A query string](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%204_Python%20for%20Data%20Science%20and%20AI/Module%205_APIs%20and%20Data%20Collection/Lesson%202_REST%20APIs%20%26%20HTTP%20Requests/A%20query%20string.png)


## Lesson 3_Web Scraping

- Web scraping in Python involves extracting and parsing data from websites to gather information for various applications, using libraries like Beautiful Soup and requests.

  - HTML comprises text surrounded by blue text elements enclosed in angular brackets called tags.

  - You can select an HTML element on a web page to inspect the webpage.

  - Web pages may also contain CSS and JavaScript along with HTML elements.

  - Each HTML document is like an HTML Tree, which may contain strings and other tags.

  - Each HTML table is comprised of table tags and is structured with elements such as rows, headers, body and so on.

[Reading: Web Scraping and HTML Basics](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTURldmVsb3BlclNraWxsc05ldHdvcmstUFkwMTAxRU4tU2tpbGxzTmV0d29yay9sYWJzL2xhYi9tb2R1bGVfNS9XZWJTY3JhcGluZ19yZWFkaW5nLm1kP3Q9MTc1MDI0MjYzNCIsInRvb2xfdHlwZSI6Imluc3RydWN0aW9uYWwtbGFiIiwiYXRsYXNfZmlsZV9pZCI6MTA4NDksImFkbWluIjpmYWxzZSwiaWF0IjoxNzU3NDQ4MzE0fQ.u1Gcsc2xt_HHc5UuZ7Box_XgPclpI8oPRzF5adVPnHE)

[Reading: Web Scraping - A Key Tool in Data Science](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-PY0101EN-SkillsNetwork/labs/mod_5/additional_webscraping.md.html)

[Reading: Web Scraping Tables using Pandas](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTURldmVsb3BlclNraWxsc05ldHdvcmstUFkwMTAxRU4tU2tpbGxzTmV0d29yay9sYWJzL21vZF81L3dlYnNjcmFwaW5nX3VzaW5nX3BhbmRhcy5tZD90PTE3NTAyNDk4NTIiLCJ0b29sX3R5cGUiOiJpbnN0cnVjdGlvbmFsLWxhYiIsImF0bGFzX2ZpbGVfaWQiOjEwODU3LCJhZG1pbiI6ZmFsc2UsImlhdCI6MTc1NzQ0ODMxNn0.M6a-Belm2yynClG-DP_DXcL7e3rEV41w65506nukrmQ)


## Lesson 4_Working with Files

- Tabular data can also be extracted from web pages using the `read_html` method in Pandas.

- Beautiful Soup in Python is a library for parsing and navigating HTML and XML documents, making extracting, and manipulating data from web pages more accessible.

- To parse a document, pass it through the Beautiful Soup constructor to get a beautiful soup object representing the document as a nested data structure.

- Beautiful soup represents HTML as a set of tree-like objects with methods to parse the HTML.

![Working with Files](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%204_Python%20for%20Data%20Science%20and%20AI/Module%205_APIs%20and%20Data%20Collection/Lesson%204_Working%20with%20Files/Working%20with%20Files.png)

<tr>Table Rows 
<td>Table Cells 
  
- Navigable string is like a Python string that supports beautiful soup functionality.

- find_all is a method used to extract content based on the tag’s name, its attributes, the text of a string, or some combination of these.

- The find_all method looks through a tag’s descendants and retrieves all descendants that match your filters.

- The result is a Python iterable like a list.

```
table_rows=table_bs.find_all('tr')
table_rows


#result
#[<tr><td id="flight">Flight No</td><td>Launch site</td> <td>Payload mass</td></tr>,
 <tr> <td>1</td><td><a href="https://en.wikipedia.org/wiki/Florida">Florida<a></a></a></td><td>300 kg</td></tr>,
 <tr><td>2</td><td><a href="https://en.wikipedia.org/wiki/Texas">Texas</a></td><td>94 kg</td></tr>,
 <tr><td>3</td><td><a href="https://en.wikipedia.org/wiki/Florida">Florida<a> </a></a></td><td>80 kg</td></tr>]
```

- File formats refer to the specific structure and encoding rules used to store and represent data in files, such as .txt for plain text or .csv for comma-separated values.

- Python works with different file formats such as CSV, XML, JSON, xlsx, and so on

- The extension of a file name will let you know what type of file it is and what it needs to open with.

- To access data from CSV files, we can use Python libraries such as Pandas.

- Similarly, different methods help parse JSON, XML, and other files.

[Cheat Sheet: APIs and Data Collection](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-PY0101EN-SkillsNetwork/handouts/Python%20Cheat%20Sheet%20-%20The%20Basics%20Coursera.pdf)

[Python Cheat Sheet: The Basics](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-PY0101EN-SkillsNetwork/handouts/Python%20Cheat%20Sheet%20-%20The%20Basics%20Coursera.pdf)

