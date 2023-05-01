# Class-09

### Ten Thousand 4
<br>

### Python Classes With Dunder (Magic, Special) Methods

#### Python classes can define special methods, also known as dunder (double underscore) methods or magic methods. These methods allow instances of the class to interact with Python's built-in functions, operators, and expressions.

#### Here are some commonly used dunder methods and what they are used for:

* __init__(self, ...): This method is called when an object of the class is created. It is used to initialize the object's attributes.

* __str__(self): This method is used to define how the object should be represented as a string. It is called when the str() function is used on the object.

* __repr__(self): This method is used to define how the object should be represented as a string for debugging purposes. It is called when the repr() function is used on the object.

* __eq__(self, other): This method is used to define how two objects of the class should be compared for equality. It is called when the == operator is used on the objects.

* __lt__(self, other): This method is used to define how two objects of the class should be compared for less than. It is called when the < operator is used on the objects.

* __len__(self): This method is used to define the length of the object. It is called when the len() function is used on the object.

* __getitem__(self, key): This method is used to define how an item should be retrieved from the object using square bracket notation. It is called when the object is indexed with square brackets.

* __setitem__(self, key, value): This method is used to define how an item should be set in the object using square bracket notation. It is called when the object is assigned a value using square brackets.

* __delitem__(self, key): This method is used to define how an item should be deleted from the object using square bracket notation. It is called when the del statement is used on an item in the object.

* __iter__(self): This method is used to define how the object should be iterated over. It is called when the object is used in a for loop.

* __next__(self): This method is used to define what the next item in the iteration should be. It is called when the next item in the iteration is requested.

#### These are just a few of the many dunder methods that can be defined in a Python class. By using these methods, you can make your classes more intuitive and easier to work with.


---
<br>

### Basic Statistics in Python — Probability

#### In Python, the random module provides a way to generate random numbers, which can be used to simulate probability experiments. Here are some basic probability functions in Python:

- random.random(): This function generates a random float between 0 and 1.

- random.uniform(a, b): This function generates a random float between a and b.

- random.randint(a, b): This function generates a random integer between a and b (inclusive).

- random.choice(seq): This function randomly selects an item from the given sequence.

- random.shuffle(seq): This function shuffles the items in the given sequence randomly.

- random.sample(seq, k): This function randomly selects k items from the given sequence without replacement.
<br>

#### In addition to the random module, Python also has the statistics module, which provides a way to perform basic statistical calculations on a list of numbers. Here are some basic statistics functions in Python:

- statistics.mean(data): This function calculates the arithmetic mean of the given data.

- statistics.median(data): This function calculates the median of the given data.

- statistics.mode(data): This function calculates the mode of the given data.

- statistics.stdev(data): This function calculates the standard deviation of the given data.

- statistics.variance(data): This function calculates the variance of the given data.
<br>

#### To use these functions, you need to import the statistics module first, like this:
```
import statistics

data = [1, 2, 3, 4, 5]
print(statistics.mean(data))   # Output: 3.0
print(statistics.median(data)) # Output: 3
print(statistics.mode(data))   # Output: 1
print(statistics.stdev(data))  # Output: 1.5811388300841898
print(statistics.variance(data)) # Output: 2.5
```
---
<br>

### What is the purpose of dunder methods in Python? Provide an example of a commonly used dunder method.

#### Python is to provide a way to customize the behavior of objects in Python. These methods are called by Python's built-in functions, operators, and expressions, and allow objects to interact with Python in a more natural way.

#### For example, the __len__ method is a commonly used dunder method that allows objects to define their length. By defining __len__, objects can be used with the built-in len() function, as well as with other functions and operators that rely on the length of an object.
<br>

#### Example:
```
class MyList:
    def __init__(self, data):
        self.data = data
    
    def __len__(self):
        return len(self.data)
    
my_list = MyList([1, 2, 3, 4, 5])
print(len(my_list)) # Output: 5
```

#### In this example, we define a MyList class with an __init__ method that takes a list of data and initializes an instance variable called data. We also define a __len__ method that returns the length of the data list. When we create an instance of MyList and call the len() function on it, Python calls the __len__ method to determine the length of the object.

#### This is just one example of how dunder methods can be used to customize the behavior of objects in Python. There are many other dunder methods that can be defined to provide even more customization options.

---
<br>

### In the video “AI Guru makes $238,800 with misleading paid course,” what was the main ethical issue raised concerning the use of developers’ work, and how might this have been avoided?

#### In the video "AI Guru makes $238,800 with misleading paid course," the main ethical issue raised was the use of developers' work without their permission or proper attribution. The AI guru in question was accused of copying code from open source repositories and incorporating it into his paid course without giving credit to the original developers.

#### This type of behavior is not only unethical, but it also violates the principles of intellectual property and could potentially lead to legal consequences. Developers have the right to protect their work and should be given proper credit and compensation for their contributions.

#### To avoid this issue, the AI guru could have taken a more ethical approach by properly crediting the original developers and obtaining permission to use their code. This could have been done by including a list of references or acknowledgments in the course materials or by contacting the original developers directly to request permission.

#### Alternatively, the AI guru could have developed his own original code and content for the course, rather than relying on others' work. While this may have required more time and effort, it would have been a more ethical and legitimate approach to creating and selling a paid course.

---
<br>

### Describe the Python statistics module and give an example of a function within the module that can be used to perform a common statistical operation.

#### The Python statistics module is a built-in module that provides a set of functions for performing basic statistical operations on data in Python. Some of the common statistical operations that can be performed using this module include calculating the mean, median, mode, variance, and standard deviation of a set of data.
<br>

#### Here's an example of a function within the statistics module that can be used to perform a common statistical operation:
```
import statistics

data = [1, 2, 3, 4, 5]

# calculate the mean
mean = statistics.mean(data)
print(mean) # Output: 3

# calculate the median
median = statistics.median(data)
print(median) # Output: 3

# calculate the mode
mode = statistics.mode(data)
print(mode) # Output: Raises StatisticsError, no unique mode

# calculate the variance
variance = statistics.variance(data)
print(variance) # Output: 2.5

# calculate the standard deviation
stdev = statistics.stdev(data)
print(stdev) # Output: 1.5811388300841898
```

#### In this example, we import the statistics module and define a list of data. We then use the mean(), median(), mode(), variance(), and stdev() functions from the statistics module to calculate the mean, median, mode, variance, and standard deviation of the data, respectively. Finally, we print the results to the console.

#### Note that the mode() function raises a StatisticsError if there is no unique mode in the data, meaning that there are multiple values with the same maximum frequency. In this case, the function cannot determine a unique mode and raises an error.

---
<br>

**-Esmail Jawabreh**