|[Table of Contents](/00-Table-of-Contents.md)|
|---|

---

## User Functions

Python functions are blocks of reusable code that can be called to accomplish some sort of functionality. Functions are meant to split up the code into functionally organized code that can be reused. In Python, you do not have to return a value.

To define a function use: 

**def function\_name\(parameters\):**

```python
def function_name(parameters):
    x = 0 # What we want to return

    return x # What we return
```

**With return value:**

```python
def name_upper(name):
    name = name*2
    return name
print(name_upper('Cao'))
```

**With no return value:**

```python
def name_upper(name):
    <code>
    print(name)
```
### Calling a Function

To call a function, you simply call the function name and pass in any needed arguments. If the function returns a variable, it is wise to call the function and direct the return value into a variable.

```python
# Lets print a name
print_name('SrA. Snuffy')
```

**Another example:**

```python
def divisible_by(num, amount):
    i = 1.0
    while (num / i >= 1 and amount > 0):
        if num % i == 0:
            print("{} divided by {} equals: {}".format(num, i, num / i))
            amount -= 1
        i += 1
divisible_by(900, 10)
```

### Parameters and Arguments

#### Parameters

Parameters are defined within the parentheses; they are undefined variables that you want to use within the function. This keeps the global scope clean. We can specify **default parameter** values as well as specify type. A lot of this can be done within the parentheses... but this can lead to unexpected problems. Before we get to default parameters, let's go over a very important topic.

**Copies vs References**

Things are different in Python. Objects are never copied during a function call... **EVER**. Function parameters are names, that's it. We bind these names to the objects we pass. So in a way, it may seem we are copying objects... but we aren't. Nor does it always seem that way. We are dealing with objects through and through, so this changes how things are done.

* As stated above, parameters are just names. When we pass arguments \(and all arguments are objects because everything is an object in Python\), we are binding these objects to these names. 
* As we've learned, objects are mutable or immutable. The same applies here. 
  * Objects that are **immutable** may appear like they are being copied. Because really, there is no way for you to modify the originals without utilizing the **global** keyword or through reassignment. Instead what happens, when you do **varname =** \(reassigning and not the same as varname\[\] =\), you are creating a _new_ name binding within the function's scope. Changes made within this scope will not be present on other existences of said object in other scopes. 
  * On the other hand, objects that are **mutable** may appear like they are being referenced, sometimes they may appear like they are being copied. The above statement is still true. But things go a step farther. When using methods or other mutable actions to act on a mutable object, you will modify the object in all scopes. It's still the same object and no new name binding was created. Let's see some examples to break this down further:

**Example of Modification**

```python
x = [1,2,3,4] # here we create a global list

def test(x):
    x[1] = 20           # here we are modifying the mutable object via indexing
    x.append(50)        # here we are modifying the mutable object via method

test(x)

print(x)

# output: 1,20,3,4,50
```

**Example of Name Binding**

```python
x = [1,2,3,4] # here we create a global list

def test(x):
    x = [1,2,3,4,5]
    x.append(200)

test(x)

print(x)

# output: 1,2,3,4
```

#### Default Parameters

**Common Way \(but risky\)**

```python
def divisible_by(num, amount = 5):
    i = 1.0
    while (num / i >= 1 and amount > 0):
        if num % i == 0:
            print("{} divided by {} equals: {}".format(num, i, num / i))
            amount -= 1
        i += 1
divisible_by(900, 10)
```

**Safe Way**

This forces the default arguments to be evaluated each time the function is called. This is especially important with mutable default objects.

```python
# Checks all numbers that can be divided into num... up until amount has been reached or we reach divide by self
def divisible_by(num, amount=None):
    if amount is None:
        amount = 5

    i = 1.0
    while (num / i >= 1 and amount > 0):
        if num % i == 0:
            print("{} divided by {} equals: {}".format(num, i, num / i))
            amount -= 1
        i += 1
divisible_by(900)
```

#### Arguments

Arguments are defined variables that you pass on the function call.

**Examples of parameters and arguments:**

```python
def sales_tax(amount): # function and parameter 'amount'
    rate = 0.0625
    tax_total = amount * rate
    total = tax_total + amount
    print(total)

sales_tax(200) # Function call and argument 200
```

**\*args and \*\*kwargs**

* \*args are used to pass a non-keyworded, variable-length argument list.
* \*\*kwargs is used to pass a keyworded, variable-length argument list.
* A keyword argument is where you provide a name to the variable as you pass it into the function.
* kwargs are placed in dictionaries.

**Example:**

```python
def my_func1(*args):
    for arg in args:
        print('arg: ', arg)
        print(type(args))
def my_func2(**kwargs):
    for key, value in kwargs.items():
        print(key, value)
my_func1('two', 3, 'four', 5)
my_func2(a = 12, b = 'abc')
```

### Cmdline Arguments

Arguments can also be passed through the command line or terminal.

#### Old:

Know both versions. The new version works in both Python 2.7 and 3.x

```python
import sys

args = str(sys.argv)
print(sys.argv[0]) # The name of the program is always argv[0]
for i in range(len(sys.argv)):
    print 'args[%d]: %s' % (i, sys.argv[i])

# Input Example: python2 test.py hello world "Hello World"
# What is the output?
```

#### New:

```python
import argparse

parser = argparse.ArgumentParser(description='This is a demo')
parser.add_argument('-i','--input',help='Input arg', required=True)
args = parser.parse_args()

print(args.input)

# Input Example: python2 test.py -i test
```

**Reference: Argparse Tutorial**

### Returning

With functions, you have the choice to return a variable. This is done so that the function becomes it's own local scope... keeping the global scope clean from any interference that the function may cause. If you want to bring a local function variable outside of the local scope... return a variable. With that said, returned values can be reassigned. If you find yourself having to return a ton of variables, either use a sequence or mapping object or split up the functionality into additional functions.

```python
def create_initials(first_name, last_name):
    initials = first_name[0].upper() + last_name[0].upper()
    return initials

initials = create_initials("jack", "black")
print(initials)
```

### Pass by Reference

Pass by Object Reference simply means that objects passed to the functions are referenced. This is technically what Python does by default. Since the objects are referenced, it can be easy to change the contents of that object; especially mutable objects.

```python
#Define the function
def append_one(a):
    a.append(1)

# Declare and set a variable
a = [0]
# Pass that variable by reference to the function append_one()
append_one(a)
print(a)

# Since the function acted on a mutable variable... the contents of the object were changed.
[0, 1]
```

**Practical Example**

The following code contains a bit of everything we have learned including some things we have not learned. This is a more robust and error/hack proof version of divisible\_by that we looked at above.

```python
"""
Checks a certain range of numbers to see if they can divide into a user specified num
"""
# Program main, runs at start of program
def launch():
    num = raw_input('What number would you like to check?')
    amount = raw_input('How many numbers do you want to check?')

    if isInt(num) == False or isInt(amount) == False:
        print("You must enter an integer")
        launch() 
    elif int(amount) < 0 or int(num) < 0:
        print("You must enter a number greater than 0")
        launch() 
    else:
        divisible_by(int(num), int(amount))

# Checks num divisable numbers up to amount or itself
def divisible_by(num, amount):
    i = 1.0
    while (num / i >= 1 and amount > 0):
        if num % i == 0:
            print('{} is divsible by {}'.format(int(num), int(i)))
            amount -= 1
        i += 1

# Checks if string represents an int
def isInt(x):
    try:
        int(x) ###
        return True
    except ValueError:
        return False

launch()
```

---

|[Next Topic](/04_functions/03_lambda_functions.md)|
|---|
