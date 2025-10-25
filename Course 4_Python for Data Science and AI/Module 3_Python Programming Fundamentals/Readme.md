# Summary: Python Programming Fundamentals

Congratulations! You have completed this module. At this point, you know that: 

## Lesson 1_Conditions and Branching

- Python conditions use “if” statements to execute code based on true/false conditions created by comparisons and Boolean expressions.

- Comparison operations require using comparison operators such as == (equal to), > (greater than), and < (less than).

- Python uses the "!=" operator to determine whether two values are not equal.

- You can compare integers, strings, and floats.

- Python branching directs program flow by using conditional statements (for example, if, else, elif) to execute different code blocks based on conditions or tests.

- You can use the "if" statement with conditions to define actions if true.

- To perform actions when all previous conditions are false, you can use the "else" statement without a condition.

- The elif statement allows for additional checks only if the initial condition is false.

```
player_name = "Michael Phelps"
sport = "Swimming"
achievements = 23

if  or achievements < 10 and sport != "Soccer":
    print(f"{player_name} plays {sport} and has only {achievements} achievements.")
else:
    print(f"{player_name} does not meet the criteria.")
```

- To execute various operations on Boolean values, we use Boolean logic operators.

[Conditions and Branching](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTURldmVsb3BlclNraWxsc05ldHdvcmstUFkwMTAxRU4tU2tpbGxzTmV0d29yay9sYWJzL01vZHVsZV8zL0NvbmRpdGlvbmFsX2JyYW5jaGluZ19SZWFkaW5nLm1kP3Q9MTc0ODUwMTU4OCIsInRvb2xfdHlwZSI6Imluc3RydWN0aW9uYWwtbGFiIiwiYXRsYXNfZmlsZV9pZCI6MTA4NTMsImFkbWluIjpmYWxzZSwiaWF0IjoxNzU3NDQ4MzE1fQ.S6-Wtb6sQB8YBU_zglwQGqyE6UBq-HXv0jalhLzUVWM)
  
  
## Lesson 2_Loops
- Python loops are control structures that automate repetitive tasks and iterate over data structures like lists or dictionaries.

- The range() function generates a sequence of numbers with a specified start, stop, and step value for loops in Python.

- A for loop in Python iterates over a sequence, such as a list, tuple, or string, and executes a block of code for each item in the sequence.


# Write a Python program using a for loop that prints numbers from 1 to 15 but:
# Skips multiples of 3
# Stops the loop if the number is greater than 12

```
for i in range(1, 16):
    if i % 3 == 0:
        continue  # skip multiples of 3
    if i > 12:
        break     # stop if number > 12
    print(i)
```

- A while loop in Python executes a block of code as long as a specified condition remains true.

```
# Write a while loop to copy the strings 'orange' of the list squares to the list new_squares. Stop and exit the loop if the value on the list is not 'orange':

squares = ['orange', 'orange', 'purple', 'blue ', 'orange']
new_squares = []
i = 0
while(i < len(squares) and squares [i] == 'orange'):
    new_squares.append(squares[i])
    i = i + 1 
print (new_squares)

# Result is:  ['orange', 'orange']
```
  
[Loops in Python](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTURldmVsb3BlclNraWxsc05ldHdvcmstUFkwMTAxRU4tU2tpbGxzTmV0d29yay9sYWJzL2xhYi9Nb2R1bGVfMy9sb29wX3JlYWRpbmcubWQ_dD0xNzQ2MTE4ODIyIiwidG9vbF90eXBlIjoiaW5zdHJ1Y3Rpb25hbC1sYWIiLCJhdGxhc19maWxlX2lkIjoxMDgyNywiYWRtaW4iOmZhbHNlLCJpYXQiOjE3NTc0NDgzMDZ9.B3qqXP3nJlf0dj1ZXXGalwaNzFp-jiu1xjLhvKdr_VI)

  
## Lesson 3_Functions
- Python functions are reusable code blocks that perform specific tasks, take input parameters, and often return results, enhancing code modularity and reusability.

- You may or may not have written the codes that are often included in functions.

- Python has a set of built-in functions such as "len" to find the length of a sequence or "sum" to find the total sum of a sequence.

- The "sorted" function creates a new sorted list, while "sort" sorts items in the original list.

- You can also create your own functions in Python.

- To ensure clarity and organization and facilitate understanding and maintenance of the code, developers must document functions using a documentation string enclosed in three quotes.

- The help command will return the documentation defined for a particular function.

- A function can have multiple parameters.

- If a function does not include a return statement, it returns None by default.

- You can use the "pass" keyword in a function to indicate that it does nothing (a placeholder for future code).

- A function will usually perform more than one task.

- In Python, the scope of a variable determines where you can access or modify that variable. Global scope allows access from anywhere, while local scope restricts it to a block or function.

# Example of ***global*** variable
```

myFavouriteBand = "AC/DC"

def getBandRating(bandname):
    if bandname == myFavouriteBand:
        return 10.0
    else:
        return 0.0

print("AC/DC's rating is:", getBandRating("AC/DC"))
print("Deep Purple's rating is:",getBandRating("Deep Purple"))
print("My favourite band is:", myFavouriteBand)
```



```
# Example of ***local*** variable

def getBandRating(bandname):
    myFavouriteBand = "AC/DC"
    if bandname == myFavouriteBand:
        return 10.0
    else:
        return 0.0

print("AC/DC's rating is: ", getBandRating("AC/DC"))
print("Deep Purple's rating is: ", getBandRating("Deep Purple"))
print("My favourite band is", myFavouriteBand)
```

- In Python, a programmer defines a local variable within a specific block or function, which can only be accessed or modified within that block or function.

- In Python, a global variable is a variable defined at the top level of a program that any part of the code can access or modify.

```
def freq(string, passedkey):
    
    #step1: A list variable is declared and initialized to an empty list.
    words = []
    
    #step2: Break the string into list of words
    words = string.split() # or string.lower().split()
    
    #step3: Declare a dictionary
    Dict = {}
    
    #step4: Use for loop to iterate words and values to the dictionary
    for key in words:
        if(key == passedkey):
            Dict[key] = words.count(key)
        
    #step5: Print the dictionary
    print("The total count of word is:",Dict)
    
#step6: Call function and pass string in it
freq("Mary had a little lamb Little lamb, little lamb Mary had a little lamb.Its fleece was white as snow And everywhere that Mary went Mary went, Mary went \
Everywhere that Mary went The lamb was sure to go","little" )


# Result: The total count of word is: {'little': 3}
```

[Python Functions](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTURldmVsb3BlclNraWxsc05ldHdvcmstUFkwMTAxRU4tU2tpbGxzTmV0d29yay9sYWJzL01vZHVsZV8zL2Z1bmN0aW9uX3JlYWRpbmcubWQ_dD0xNzQyNTQzMzUyIiwidG9vbF90eXBlIjoiaW5zdHJ1Y3Rpb25hbC1sYWIiLCJhdGxhc19maWxlX2lkIjoxMDgzMSwiYWRtaW4iOmZhbHNlLCJpYXQiOjE3NTc0NDgzMDd9.98wasEUy76hTI9l1veZxZQhkwqcK1ast8BEvXWWWF_A)
  
## Lesson 4_Exception Handling
- Exception handling in Python is a mechanism for managing and responding to errors and exceptions that may occur during program execution, preventing them from crashing the program.

- In Python, you use the "try-except" statement to attempt a block of code and specify alternative actions to execute if an error occurs, allowing you to handle exceptions. 

- In Python, you use the "try-except-else" statement to attempt a block of code, handle exceptions in the "except" block, and execute code in the "else" block when no exceptions occur. 

- Python developers use the "try-except-else-finally" statement to attempt a block of code, catch exceptions in the "except" block, execute code in the "else" block when no exceptions occur, and ensure that the "finally" block always runs, regardless of whether exception was raised or not.

```
```
  
[Exception Handling](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTURldmVsb3BlclNraWxsc05ldHdvcmstUFkwMTAxRU4tU2tpbGxzTmV0d29yay9sYWJzL0V4Y2VwdGlvbl9oYW5kbGluZ19SZWFkaW5nLm1kP3Q9MTc0NjExODc1NiIsInRvb2xfdHlwZSI6Imluc3RydWN0aW9uYWwtbGFiIiwiYXRsYXNfZmlsZV9pZCI6MTA4MTcsImFkbWluIjpmYWxzZSwiaWF0IjoxNzU3NDQ4MzA0fQ.Bayq6CpYG5UOwdCl_38c8OCm9QI2RmEBu2R4shXIQ6o)

## Lesson 5_Objects and Classes
- In Python, objects are instances of classes that encapsulate data and behavior, serving as the foundation for creating and working with various data types and custom data structures.

- To determine the type of an object in Python, you can use the `type()` command.

- Methods may modify an object’s internal state, but the object’s type usually remains the same.

- Classes in Python are blueprints for creating objects, defining their attributes and methods, enabling code organization, and object-oriented programming.

- Function "init" is a special method used to initialize data attributes.

- We can create instances of a class in Python.

- Data attributes consist of the data defining the objects.

- Methods are functions that interact and change the data attributes.

- The method has a function that requires the self as well as other parameters.

[Objects and Classes](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTURldmVsb3BlclNraWxsc05ldHdvcmstUFkwMTAxRU4tU2tpbGxzTmV0d29yay9sYWJzL2NsYXNzZXNfYW5kX29iamVjdF9SZWFkaW5nLm1kP3Q9MTc0NjExODgxMCIsInRvb2xfdHlwZSI6Imluc3RydWN0aW9uYWwtbGFiIiwiYXRsYXNfZmlsZV9pZCI6MTA4MzksImFkbWluIjpmYWxzZSwiaWF0IjoxNzU3NDQ4MzEwfQ.HSMbV_vJYr1TH-RjHPBFaPxnEJcabeofFCssvdPEZHo)


## Lesson 6_Practice with Python Programming Fundamentals
[Python Programming Fundamentals Cheat Sheet](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTURldmVsb3BlclNraWxsc05ldHdvcmstUFkwMTAxRU4tU2tpbGxzTmV0d29yay9sYWJzL2hhbmRvdXRzL0NoZWF0X1NoZWV0X1dlZWstMy5tZD90PTE3NTAzMTAxNTciLCJ0b29sX3R5cGUiOiJpbnN0cnVjdGlvbmFsLWxhYiIsImF0bGFzX2ZpbGVfaWQiOjEwODI5LCJhZG1pbiI6ZmFsc2UsImlhdCI6MTc1NzQ0ODMwN30.32ZV_tRoDobGor7tmyZd7ZlK2Be2xd-ozNhpsXwr0HM)

[Python Quiz Reference Sheet](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-PY0101EN-SkillsNetwork/labs/Module%203/Python_reference_sheet.pdf?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkPY0101ENSkillsNetwork19487395-2022-01-01)
