# py2cfg

## Description

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

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>
