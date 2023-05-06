# Class-03

### FileIO & Exceptions
<br>

#### In Python, File Input/Output (IO) refers to the process of reading data from or writing data to a file. 
#### Python provides built-in functions and modules to perform these operations.

#### The most commonly used functions for working with files are:

<ul>
<br>

### <li><strong>open()</strong></li>

#### This function opens a file and returns a file object. 
#### You need to specify the file name and the mode in which you want to open the file. 
#### For example, if you want to open a file named example.txt in read mode, you can use the following code:
```
file = open("example.txt", "r")
```
#### The mode argument can be "r" for read mode, "w" for write mode, "a" for append mode, "x" for exclusive creation mode, and "b" for binary mode.


<br>

### <li><strong>read()</strong></li>

#### This function reads the contents of a file. 
#### You can specify the number of bytes you want to read, or leave it blank to read the entire file. 
#### For example, to read the entire file, you can use the following code:
```
content = file.read()
```
#### You can also specify the number of bytes you want to read, like this:
```
content = file.read(10)
```
#### This will read the first 10 bytes of the file.


<br>

### <li><strong>write()</strong></li>

#### This function writes data to a file. 
#### You need to specify the data you want to write to the file. 
#### For example, to write a string to a file, you can use the following code:
```
file.write("This is a sample text.")
```
#### Note that if you open a file in write mode ("w"), it will erase the contents of the file if it already exists. 
#### If you want to add data to the file without erasing its contents, you can use append mode ("a") instead.


<br>

### <li><strong>close()</strong></li>


#### This function closes the file you have opened. 
#### It is important to close the file when you are done with it to free up system resources. 
#### For example, to close a file, you can use the following code:
```
file.close()
```

<br>
</ul>

#### In addition to these basic functions, Python provides several other functions and methods for working with files, such as: 

<ul>

<li><strong>readline()</strong> for reading a single line of a file.</li> 
<li><strong>writelines()</strong> for writing a list of strings to a file.</li>
<li><strong>seek()</strong> for changing the position of the file pointer.</li>

</ul>
<br>

#### Overall, reading and writing files in Python is a simple and efficient process thanks to the built-in functions provided by the language.
#### However, it's important to always close the file after you're done with it to prevent any issues with file corruption or memory usage.


<br>

---
<br>

### What is the purpose of the ‘with’ statement when opening a file in Python, and how does it help manage resources while reading and writing files?
<br>

#### The <strong>with</strong> statement in Python is used to open and manage files.
#### It simplifies the process of closing the file after use by automatically handling the resource management for you. 
#### When you use <strong>with</strong>  to open a file, Python automatically closes the file as soon as the block inside the with statement is exited. 
#### This ensures that the file is properly closed and minimizes the risk of data loss or corruption.
<br>

#### Here's an example:
```
with open('example.txt', 'r') as f:
    contents = f.read()
    print(contents)
```

---

### the difference between the ‘read()’ and ‘readline()’ methods for file objects in Python.
<br>

#### The <strong>read()</strong> method reads the entire contents of a file and returns it as a string. 
#### It takes an optional parameter specifying the number of bytes to read.
#### If no argument is provided, it reads the entire file. 
#### This method is useful when you need to read the entire content of a small file.
<br>

#### Here's an example:
```
with open('myfile.txt', 'r') as f:
    file_contents = f.read()
    print(file_contents)
```
<br>

#### The <strong>readline()</strong> method reads a single line from a file and returns it as a string. 
#### It reads up to and including the first newline character (\n). 
#### If no newline character is found, it reads the entire remaining line. 
#### This method is useful when you need to read a file line by line.
<br>

#### Here's an example to read a single line from a file:
```
with open('myfile.txt', 'r') as f:
    line = f.readline()
    print(line)
```
<br>

#### and here's an example to read the entire file line by line:
```
with open('myfile.txt', 'r') as f:
    for line in f:
        print(line)
```
<br>

#### In general, you should use <strong>read()</strong> when you need to read the entire file at once, and <strong>readline()</strong> when you need to read the file line by line.

---
<br>

### The concept of exception handling in Python. 
### How can the ‘try’, ‘except’, and ‘finally’ blocks be used to handle exceptions and ensure proper execution of code? 
<br>

#### Exception handling is a programming concept used to handle runtime errors that can occur in a program. 
#### In <strong>Python</strong>, exceptions can be raised for various reasons such as invalid input, division by zero, or file not found, etc.
<br>

#### The <strong>try</strong>, <strong>except</strong>, and <strong>finally</strong> blocks are used in Python to handle exceptions. 
#### The <strong>try</strong> block is used to enclose the code that can potentially raise an exception. 
#### The <strong>except</strong> block is used to catch the exception and take appropriate action. 
#### The <strong>finally</strong> block is used to execute code that should be executed regardless of whether an exception was raised or not.
<br>

#### Here's a simple example:
```
try:
    a = 10 / 0
    print(a)
except ZeroDivisionError:
    print("Division by zero is not allowed")
finally:
    print("This code will always execute")
```
<br>

#### In this example, 
#### The <strong>try</strong> block attempts to divide the number 10 by 0, which will raise a ZeroDivisionError.
#### The <strong>except</strong> block catches the exception and prints a message to the console. 
#### The <strong>finally</strong> block is executed regardless of whether the exception was raised or not, and it prints a message to the console.
<br>

#### Output:
```
Division by zero is not allowed
This code will always execute
```


---
<br>

### Things I want to know more about : Nothing for now.
<br>

---

**- Esmail Jawabreh**