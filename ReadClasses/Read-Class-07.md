# Class-07

### Ten Thousand 2
<br>

### Python Scope

#### Global Scope:
#### a global variable is a variable that is defined outside of any function and can be accessed from any part of the program, including inside functions.

#### When a variable is declared as global, it means that any reference to that variable within a function will refer to the global variable, not a local variable with the same name.
<br>

#### To define a global variable, you simply declare it outside of any function, like this:
```
global_var = 10
```

<br>

#### Then, to use the global variable inside a function, you declare it as global within the function, like this:
```
def my_function():
    global global_var
    print(global_var)
```

#### This will print the value of the global variable <strong>global_var</strong> inside the function <strong>my_function()</strong>. Note that without the <strong>global</strong> keyword, the function would create a new local variable with the same name instead.

#### It's important to use global variables with care, as they can make code harder to understand and maintain. In general, it's best to avoid using global variables when possible, and instead pass values between functions using function arguments and return values.

<br>
<br>

#### Local Scope:
#### In Python, local scope refers to the area of the code where a variable is defined within a function or a code block, such as an if statement or a for loop. Variables defined in local scope are only accessible within that specific function or block, and cannot be accessed from outside.
<br>

#### For example, in the following code snippet:
```
def my_function():
    x = 5
    print(x)
```

<br>

#### The variable x is defined within the local scope of the my_function() function. This means that x can only be accessed within the function and is not visible outside of it. If you were to try to print the value of x outside of the function, you would get a NameError since x is not defined in the global scope.

<br>

#### Local variables take precedence over global variables with the same name. For example:
```
x = 10

def my_function():
    x = 5
    print(x)

my_function()  # output: 5
print(x)  # output: 10
```
<br>

#### In this case, the function defines a local variable x with a value of 5, which takes precedence over the global variable x with a value of 10. When we call the function, it prints the value of the local variable x (5), and outside the function, the value of the global variable x (10) is printed.

#### It's important to use local variables to avoid naming conflicts and to keep code organized and modular. Local variables are also automatically cleaned up (deleted) when the function or code block completes, freeing up memory.

<br>
<br>

#### Nonlocal Scope:
#### In Python, the nonlocal keyword is used to refer to a variable that is defined in the outer scope of the current function, but is not a global variable. It allows you to modify a variable that is outside of the local scope of the current function, but not in the global scope.

<br>

#### For example:
```
def outer_function():
    x = "outer"
    def inner_function():
        nonlocal x
        x = "inner"
        print(x)
    inner_function()
    print(x)

outer_function()  # output: inner outer
```
<br>

#### In this example, x is defined in the outer function outer_function(), and then modified in the inner function inner_function() using the nonlocal keyword. Without nonlocal, Python would create a new local variable x inside inner_function(), instead of modifying the outer x variable.

#### Note that nonlocal can only be used inside a nested function. It cannot be used at the global scope or inside a function that is not nested within another function.

#### It's important to use nonlocal with care, as it can make code harder to understand and maintain. In general, it's best to avoid modifying variables in outer scopes and instead pass values between functions using function arguments and return values.

---
<br>


### the purpose and importance of Big O notation in the context of algorithm analysis.

#### In computer science, Big O notation is used to describe the time complexity of an algorithm, or how its performance scales with the size of the input data. It is a mathematical notation that describes the upper bound on the number of operations an algorithm takes, as a function of the size of its input.

#### The purpose of Big O notation is to provide a way to analyze and compare the performance of algorithms. By using Big O notation, we can evaluate the time and space complexity of different algorithms and determine which algorithm is more efficient for a given problem.

#### The importance of Big O notation in algorithm analysis lies in its ability to help us identify and eliminate bottlenecks in our code. It allows us to optimize our code by identifying the parts of our algorithm that are most time-consuming, and finding ways to improve their efficiency.

#### Big O notation also provides a standard language for communicating about algorithmic complexity. It allows us to compare the performance of different algorithms in a clear and concise way, and to make informed decisions about which algorithm to use for a given problem.

#### For example, consider two sorting algorithms, one with a time complexity of O(n^2) and another with a time complexity of O(n log n). By using Big O notation, we can quickly determine that the second algorithm is more efficient for large data sets, and choose to use it in our code.

#### In summary, Big O notation is an important tool in algorithm analysis that helps us evaluate the efficiency of our code, identify bottlenecks, and optimize our algorithms for better performance.

---
<br>

### how you would simulate a dice roll using Python. 
### how you would use code to calculate the probability of rolling a specific number (e.g., the probability of rolling a 6) over a large number of trials.

#### To simulate a dice roll using Python, we can use the built-in random module to generate a random integer between 1 and 6, representing the six possible outcomes of a dice roll:
```
import random

dice_roll = random.randint(1, 6)
print(dice_roll)
```

<br>

#### This code generates a random integer between 1 and 6, representing the outcome of a dice roll, and stores it in the dice_roll variable. We can then print the value of dice_roll to simulate the roll.

<br>

#### To calculate the probability of rolling a specific number (e.g., the probability of rolling a 6) over a large number of trials, we can use a loop to simulate the rolls multiple times and count the number of times the specific number is rolled. For example, to simulate 1000 dice rolls and calculate the probability of rolling a 6, we can use the following code:
```
import random

num_rolls = 1000
num_sixes = 0

for i in range(num_rolls):
    dice_roll = random.randint(1, 6)
    if dice_roll == 6:
        num_sixes += 1

probability_six = num_sixes / num_rolls
print("Probability of rolling a 6:", probability_six)
```
<br>

#### This code initializes the number of rolls and the number of times a six is rolled to zero. It then uses a loop to simulate 1000 dice rolls, and checks if each roll is a 6. If it is, it increments the num_sixes counter. Finally, it calculates the probability of rolling a 6 by dividing num_sixes by the total number of rolls, and prints the result.

<br>

#### By increasing the number of rolls, we can get a more accurate estimate of the probability of rolling a specific number, and verify that the actual probability converges to the theoretical probability of 1/6 as the number of trials increases.
---
<br>

**-Esmail Jawabreh**