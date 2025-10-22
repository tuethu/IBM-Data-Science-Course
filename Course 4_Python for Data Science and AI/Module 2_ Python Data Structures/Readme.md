# Summary: Python Data Structures

Congratulations! You have completed this module. At this point, you know that: 

## TUPLE

- In Python, we often use tuples to group related data together.Tuples refer to ordered and immutable collections of elements.

- Tuples are usually written as comma-separated elements in <ins>parentheses<ins>  “()".

- You can include strings, integers, and floats in tuples and access them using both positive and negative indices.

- You can perform operations such as combining, concatenating, and slicing on tuples.

```
genres_tuple = ("pop", "rock", "soul", "hard rock", "soft rock", \
                "R&B", "progressive rock", "disco") 
genres_tuple[3:6] # Use slicing to obtain indexes 3,4 and 5
('hard rock', 'soft rock', 'R&B') #result

```
- Tuples are <ins>immutable<ins>, so you need to create a new tuple to manipulate it.

- Tuples, termed nesting, can include other tuples of complex data types.

- You can access elements in a nested tuple through indexing.
```
"disco".find('s') #Find the index of 's' in "disco"
2 #result
 ``` 

## LIST

- Lists in Python contain ordered collections of items that can hold elements of different types and are mutable, allowing for versatile data storage and manipulation.

- A list is an ordered sequence, represented with square <ins>brackets<ins> "[]".

- Lists possess mutability, rendering them akin to tuples.

- A list can contain strings, integers, and floats; you can nest lists within it.

- You can access each element in a list using both positive and negative indexing.

- Concatenating or appending a list will result in the modification of the same list.

- You can perform operations such as adding, deleting, splitting, and so forth on a list.

  - **add (append) The `append()` method is used to add an element to the end of a list**
```
fruits = ["apple", "banana", "orange"] 
fruits.append("mango") 
print(fruits)
```

- You can perform operations such as adding, deleting, splitting, and so forth on a list.
  - **add (extend) The `extend()` method is used to add multiple elements to a list**
```
fruits = ["apple", "banana", "orange"] 
more_fruits = ["mango", "grape"] 
fruits.extend(more_fruits) 
print(fruits)
```
- You can separate elements in a list using delimiters.

- Aliasing occurs when multiple names refer to the same object.

- You can also clone a list to create another list.

[Tuple and List Cheat Sheet ](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTURldmVsb3BlclNraWxsc05ldHdvcmstUFkwMTAxRU4tU2tpbGxzTmV0d29yay9sYWJzL2hhbmRvdXRzL0NoZWF0X1NoZWV0X1dlZWstMi5tZD90PTE3NTAzMTY5NDIiLCJ0b29sX3R5cGUiOiJpbnN0cnVjdGlvbmFsLWxhYiIsImF0bGFzX2ZpbGVfaWQiOjEwODI1LCJhZG1pbiI6ZmFsc2UsImlhdCI6MTc1NzQ0ODMwNX0.pZ4GmPcAY2wsZmQWF5y2cIYhvRZUL5gJ2JM47q3JjGY).

## DICTIONARY

- Dictionaries in Python are key-value pairs that provide a flexible way to store and retrieve data based on unique keys.

- Dictionaries consist of keys and values, both composed of string elements.
```
soundtrack_dic = {"The Bodyguard":"1992", "Saturday Night Fever":"1977"}
soundtrack_dic.keys() #find the keys
dict_keys(['The Bodyguard', 'Saturday Night Fever']) #result of the keys

soundtrack_dic.values() #find the values
dict_values(['1992', '1977']) #result of the values
```
- You denote dictionaries using <ins>curly brackets<ins> {}.

- The keys necessitate immutability and uniqueness.

- The values may be either immutable or mutable, and they allow duplicates.

- You separate each key-value pair with a comma, and you can use color highlighting to make the key more visible.

- You can assign dictionaries to a variable.

- You use the key as an argument to retrieve the corresponding value.

- You can make additions and deletions to dictionaries.

```
dict_name = {} #Creates an empty dictionary
person = { "name": "John",  "age": 30, "city": "New York"}
person["Country"] = "USA" # A new entry will be created.
person["city"] = "Chicago"  # Update the existing value for the same key

```
- You can perform an operation on a dictionary to check the key, which results in a true or false output.

- You can apply methods to obtain a list of keys and values in a dictionary.


## SET

- Sets in Python are collections of unique elements, useful for tasks such as removing duplicates and performing set operations like union and intersection. Sets lack order.

- <ins>Curly brackets<ins> "{}" are helpful for defining elements of a set.
```
empty_set = set() #Creating an Empty Set 
fruits = {"apple", "banana", "orange"}
colors = ("orange", "red", "green")
```
- Sets do <ins>NOT contain duplicate<ins> items.

- A list passed through the set function generates a set containing unique elements.

- You use “Set Operations” to perform actions such as adding, removing, and verifying elements in a set.

```
fruits.add("mango")
```

- You can combine sets using the ampersand "&" operator to obtain the common elements from both sets.

- You can use the Union function to combine two sets, including both the common and unique elements from both sets.
  
```
combined = fruits.union(colors) 
common = fruits.intersection(colors) 
unique_to_fruits = fruits.difference(colors) 
sym_diff = fruits.symmetric_difference(colors)
```

- The sub-set method is used to determine if two or more sets are subsets.

```
is_subset = fruits.issubset(colors)
```

[Dictionary and Set Cheat Sheet ](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTURldmVsb3BlclNraWxsc05ldHdvcmstUFkwMTAxRU4tU2tpbGxzTmV0d29yay9sYWJzL2hhbmRvdXRzL0NoZWF0X1NoZWV0X1dlZWstMl9QYXJ0LTIubWQ_dD0xNzQ5MDI2NzU0IiwidG9vbF90eXBlIjoiaW5zdHJ1Y3Rpb25hbC1sYWIiLCJhdGxhc19maWxlX2lkIjoxMDgzNSwiYWRtaW4iOmZhbHNlLCJpYXQiOjE3NTc0NDgzMDl9.GbzFlAbl7gwY5nBE1cWFVTjNKuES7EF1Kt7i8JA6KVI).


