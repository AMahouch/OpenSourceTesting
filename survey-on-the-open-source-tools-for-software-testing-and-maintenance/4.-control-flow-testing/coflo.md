# py2cfg

{% embed url="https://pypi.org/project/py2cfg/" %}
All code, documentation, and releases can be found on this PyPi site.
{% endembed %}

## Description

py2cfg is a Python package designed to create Control Flow Graphs (CFGs) for Python3 programs, an important concept in software testing and analysis. py2cfg simplifies the generation of these CFGs and offers seamless integration with Graphviz visualization software.

The main objective of py2cfg is to provide a user-friendly tool to understand, analyze, and assess the control flow of Python programs. By producing clear and intuitive graphical representations, it aids in identifying potential issues, testing scenarios, and debugging processes. Whether the objectives involve assessing code coverage, identifying edge cases, or enhancing software reliability, py2cfg serves as a valuable tool within the software testing toolkit.

## Setup

py2cfg is a Python package, it can be easily implemented in various development environments and command-line interfaces. This setup will be using the [Visual Studio Code IDE](https://code.visualstudio.com/), but any development environment can be used



**Installation**

Install py2cfg using `pip`:

```bash
pip install py2cfg
```

The package can also be installed through the Anaconda package manager:

```bash
conda install -c conda-forge py2cfg
```



**Usage**

After installing `py2cfg`, you can use it in several ways. Below are 4 options to use the tool:

**Option 1: Run via Shell Command** If you have installed it, you can run `py2cfg` as a shell command to generate control flow graphs for Python files:

```bash
py2cfg <file.py>
```

This command will output a `<file>_cfg.svg` file in the current directory containing the colored control flow graph of the specified Python file.

**Option 2: Run with pudb3** You can also use `py2cfg` interactively with `pudb3` for debugging:

```bash
py2cfg <file.py> --debug
```

**Option 3: Via Wrapper (Without Installation)** If you prefer not to install `py2cfg`, you can run a script present in the repo, `_runner.py`, to directly generate a control flow graph of a Python program and visualize it:

```bash
cd intoreporootdir
python3 py2cfg/_runner.py path_to_my_code.py
```

**Option 4: Via Import (In  Python Code)** Whether or not you have installed `py2cfg`, you can import the module into your Python code and use the `py2cfg.CFGBuilder` class to build control flow graphs:

```python
import py2cfg

# Create a CFGBuilder object
builder = py2cfg.CFGBuilder()

# Build a control flow graph for the file "my_code.py"
cfg = builder.build_cfg("my_code.py")

# Visualize the control flow graph
cfg.build_visual(filename="my_code_cfg.svg")
```



## Demo

\***uploading video soon**\*

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

Generated this:

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1).png" alt=""><figcaption><p>fig_cfg.py</p></figcaption></figure>



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

<figure><img src="../../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
