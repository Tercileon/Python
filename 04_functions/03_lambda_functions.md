<a href="https://github.com/CyberTrainingUSAF/07-Python-Programming/blob/master/00-Table-of-Contents.md" rel="Return to TOC"> Return to TOC </a>

# Lambda Functions

It's best to start off with some examples:

**Example 1:**

```python
my_list = range(26)

print(my_list)
print(filter(lambda x: x % 2 == 0, my_list))
```

**Breaking down the first example:**
```text

lambda - the keyword to create a lambda
x - the parameter. Multiple parameters ex: lambda x,y,z:
x % 2 == 0: the execution code
my_list: the argument. Multiple args ex: lambda x,y,z: <code>, input1, input2, key

Multiple arg/param lambda: 
lambda x,y,z: (x + y) - z, input1, input2, key
```
**Example 2:**

```python
g = lambda x,y: x>y
print g(1,2)
print g(2,1)
```

As you can tell, lambdas appear to be shortened functions; specifically one lined functions. And while this is true to an extent... that is not their purpose.

Lambdas, in short, are anonymous functions. Functions without a name. They are generally passed as arguments to higher-order functions as well as a variety of other uses. Below are some of the features of a Lambda

**Lambda Features:**

* Lambda forms can take any number of arguments
* Return only one value in the form of an expression
* They cannot contain commands or multiple expressions
* It cannot be a direct call to print because lambda requires an expression
* Lambda functions have their own namespace

Due to the fact that they have their own local namespace... Lambdas cannot access variables other than those in their parameters list and globals.

### **Example:**

```python
def factorial(n):return reduce(lambda x,y:x*y,[1]+range(1,n+1))
```

### **Breakdown of a Lambda**

```python
#Define a regular function
def reg_function(x):
    return x**2

# Make it one line
def reg_function(x): return x**2

# Turn it into a lambda
new_stuff = lambda x: x**2
```

## Common Lambda Uses

#### map\(\)

* Map applies a function to all the items in an input\_list. That function can be a lambda. 

#### filter\(\)

* Filter creates a list of elements for which a function returns true. 

#### reduce\(\)

* Reduce accepts a function and a sequence and returns a single calculated value.

#### [Examples](http://book.pythontips.com/en/latest/map_filter.html)  

---
## Continue to Lab 4A and 4B  

<a href="https://github.com/CyberTrainingUSAF/07-Python-Programming/blob/master/04_functions/lab4a.md" > Continue to Lab 4a and 4B </a>

