# Summary: Working with Data in Python

Congratulations! You have completed this module. At this point, you know that: 

## Lesson 1_Reading and Writing Files with Open

- Python uses the open() function and allows you to read and write files, providing access to the content within the file for reading. It also allows overwriting it for writing and specifies the file mode (for example, r for reading, w for writing, a for appending).

  - To read a file, Python uses an open function along with r.

  - Python uses the <ins>**open with**</ins> function to read and process a file attribute, that is, from open to close.

  - In Python, you use the <ins>**open**</ins> method to edit or overwrite a file.

```
with open(example1, "r") as file1:
    print(file1.readline(20)) # does not read past the end of line
    print(file1.read(20)) # Returns the next 20 chars
```


  - To write a file, Python uses the <ins>**open**</ins> function along with w.
```
with open('/Example2.txt', 'w') as writefile:
    writefile.write("Overwrite\n")
with open('/Example2.txt', 'r') as testwritefile:
    print(testwritefile.read())
 ```
   
  - In Python, "a" indicates that the program has appended to the file.
```
with open('/Example2.txt', 'a+') as testwritefile:
    testwritefile.write("This is line E\n")
    print(testwritefile.read())
```
    
  - In Python, “\n” signifies that the code should start on a new line. 

  - Python uses various methods to print lines from attributes.


## Lesson 2_Pandas

- Pandas is a powerful Python library for data manipulation and analysis, providing data structures and functions to work with structured data like data frames and series.

  - You import the file (panda) by using the import command followed by the file name. 

  - In Python, you use the <ins>**as**</ins> command to provide a shorter name for the file.
```
from pyodide.http import pyfetch
import pandas as pd

filename = "https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/LXjSAttmoxJfEG6il1Bqfw/Product-sales.csv"

async def download(url, filename):
    response = await pyfetch(url)
    if response.status == 200:
        with open(filename, "wb") as f:
            f.write(await response.bytes())


await download(filename, "Product-sales.csv")
df = pd.read_csv("Product-sales.csv")
```
  - In Pandas, you use a data frame (df) to specify the files to read.

```
x = df['Product']
x

#Output as following
0        Laptop
1    Smartphone
2    Desk Chair
3      Notebook
4       Monitor
Name: Product, dtype: object

```

  - DataFrames consist of rows and columns.  

  - You can create new DataFrames by using the column or columns of a specific DataFrame.  

  - We can work with data in a DataFrames and save the results in different formats.

  - In Python, you use the <ins>**Unique**</ins> method to determine unique elements in a column of the DataFrames.

```
df.iloc[0, 0] # Access the value on the first row and the first column
```

  - You use the inequality operator along with df to assign a Boolean value to the selected column in DataFrames.

```
new_index=['a','b','c','d','e']
df_new=df
df_new.index=new_index
df_new.loc['a', 'CustomerCity']
df_new.loc['a':'d', 'CustomerCity']
```

  - You save a new DataFrame as a different DataFrame, which may contain values from an earlier DataFrame.
    

## Lesson 3_Numpy in Python

- NumPy is a Python library for numerical and matrix operations, offering multidimensional array objects and a variety of mathematical functions to work with data efficiently.

  - NumPy is a basis for Pandas.

  - A NumPy array or ND array is similar to a list, usually of a fixed size with the same kind of element.


- A one-dimensional NumPy array is a linear sequence of elements with a single axis, like a traditional list, but optimized for numerical computations and array operations.

  - You can access elements in a NumPy using an index. 

  - You use the attribute <ins>**dtype**</ins> to get the data type of the array elements. 

  - You use <ins>**size**</ins> and <ins>**ndim**</ins> to get the size and dimension of the array, respectively. 

  - You can use indexing and slicing methods in NumPy. 

  - Vector additions are widely used operations in Python. 

  - Representing vector addition with line segments or arrows is useful.

  - NumPy codes work much faster, which is helpful with lots of data.

  - You perform vector subtraction by replacing the addition sign with a negative sign. 

  - Multiplying an array by a scalar in Python entails multiplying each element of the array by the scalar value, leading to a new array in which each element scales by the scalar.

  - Hadamard product refers to the element-wise multiplication of two arrays of the same shape, resulting in a new array where each element is the product of the corresponding elements in the input arrays.

  - The dot product in Python is the sum of the element-wise products of two arrays, often used for vector and matrix operations to find the scalar result of multiplying corresponding elements and summing them.

  - When working with NumPy, it is common to utilize libraries like Matplotlib to create graphs and visualizations from numerical data stored in NumPy arrays.


- A two-dimensional NumPy array is a grid-like structure with rows and columns suitable for representing data as a matrix or a table for numerical computations.

  - In NumPy, "shape" refers to an array's dimensions (number of rows and columns), indicating its size and structure.

  - You use the attribute "size" to obtain the size of an array. 

  - You use rectangular attributes to access the various elements in an array.

  - You use a scalar to multiply elements in NumPy.
