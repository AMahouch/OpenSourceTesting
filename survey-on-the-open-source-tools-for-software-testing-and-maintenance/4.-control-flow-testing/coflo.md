# py2cfg

## Description

py2cfg is a Python package designed to create Control Flow Graphs (CFGs) for Python3 programs, an important concept in software testing and analysis. py2cfg simplifies the generation of these CFGs and offers seamless integration with Graphviz visualization software for easy visualization.

The main objective of py2cfg is to allow software testers and analysts by providing a user-friendly tool to understand, analyze, and assess the control flow of Python programs. By producing clear and intuitive graphical representations, it aids in identifying potential issues, testing scenarios, and debugging processes. Whether the objectives involve assessing code coverage, identifying edge cases, or enhancing software reliability, py2cfg serves as a valuable tool within the software testing toolkit



{% embed url="https://pypi.org/project/py2cfg/" %}

## Setup



## Demo

will record video soon



python code

````python
# fib.py

def fib():
    a, b = 0, 1
    while True:
        yield a
        a, b = b, a + b

fib_gen = fib()
for _ in range(10):
    next(fib_gen)

```
````

generates this:

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>



python code

````python
# example.py

# Conditional statements (if-elif-else)
x = 10

if x < 0:
    print("x is negative")
elif x == 0:
    print("x is zero")
else:
    print("x is positive")

# For loop
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print("I like", fruit)

# While loop
count = 0
while count < 5:
    print("Count:", count)
    count += 1

# Exception handling (try-except)
try:
    result = 10 / 0  # Division by zero to trigger an exception
except ZeroDivisionError:
    print("Division by zero is not allowed")
else:
    print("Result:", result)

```
````



generates this

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>
