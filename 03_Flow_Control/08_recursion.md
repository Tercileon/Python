<a href="https://github.com/CyberTrainingUSAF/07-Python-Programming/blob/master/00-Table-of-Contents.md" rel="Return to TOC"> Return to TOC </a>

# Recursion

Recursion is a function that calls itself. In other words a function will continue to call itself until a certain condition is met. Any problem that can be solved by recursion can be solved by using a loop. We mentioned before that it is almost always preferential to use a loop due to overhead. However, you may want to use recursion when you have a problem that needs to be broken into smaller similar problems and solve them first. 

### Base case and recursive case

**Base Case**

If the problem can be solved now, then the function solves it and returns

**Recursive Case**

If the problem cannot be solved now, then the function reduces it to smaller similar problems and calls itself to solve the smaller problem.

#### Recursion to find factorial of a number

The best way to understand is to dive in. Lets take a look at solving for n!. As a quick reminder n! is defined as:

```text
    n! = n x (n-1) x (n-2) x (n-3) x...x 3 x 2 x 1
    4! = 4 x 3 x 2 x 1 = 24
    
Base case:
    If n = 0 then   n! = 1
or  If n = 0 then   factorial(n) = 1

Recursive case:
    If n > 0 then   n! = 1 x 2 x 3 x ... n
or  If n > 0 then   factorial(n) = n x factorial(n-1)
```
Now lets translate to Python:

```python
def recursive_factorial(n):
    #base case
    if n == 0:
        return 1
    #recursive case
    else:
        return n * recursive_factorial(n-1)
```

Be sure that every time you write a recursive function that you can control the number of times it will be executed.

```python
# Endless recursion
def forever_recursion():
    annoying_message()

def annoying_message():
    print('Nudge Nudge, Wink Wink, Say No More Say No More')
    message()
```

![](../.gitbook/assets/nudge.jpg)

#### Recursion for the Fibonacci Series

A very common way to present recursion is by writing a program to calculate Fibonacci numbers. After the second number, every number in the series is the sum of the two previous numbers. The sequence is the following:
0,1,1,2,3,5,8,13,21,34,55,89,144,233,...

```text
A recursive function can have multiple base cases. Both of them return a value without making a recursive call.

Base case:
    If n = 0 then   fibonacci(n) = 0
    If n = 1 then   fibonacci(n) = 1

Recursive case:
    If n > 1 then   fibonacci(n) = fibonacci(n-1) + fibonacci(n-2)
```
Now lets translate to Python:

```python
def fibonacci(n):
    if n == 0:
        return 0
    elif n == 1:
        return 1
    else:
        return fibonacci(n-1) + fibonacci(n-2)
```