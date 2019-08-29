|[Table of Contents](/00-Table-of-Contents.md)|
|---|

---

## Modules

Modules are reusable code that can be imported into other scripts or programs. Modules are single files in either .py, .pyc or .pyo format. When a module is imported, code that is not wrapped in a function is executed and the functions themselves are added to the namespace... allowing them to be called upon.

### Module Structure

```python
#/usr/lib/python/site-packages/triangle.py

divisor_count_to_find = 500

def triangle_number(n):
    return n*(n+1)/2

def divisors(tn):
    counter = 0
    n_sqrt = int(pow(tn, 0.5))
    for i in range(1, n_sqrt + 1):
        if tn%i == 0:
            counter += 2
    if n_sqrt * n_sqrt == tn:
        counter -= 1
    return counter

def start():
    start_number = 1
    div_numbers = 0
    while (div_numbers < divisor_count_to_find):
        tn = triangle_number(start_number)
        div_numbers = divisors(tn)
        start_number += 1
    print(div_numbers)
    print(tn)

if __name__ == '__main__':
    start()
```

### Reference: [if \_\_name\_\_ == '\_\_main\_\_':](http://codenhance.com/2015/10/20/wtf-is-if-name-equals-main.html)

In other words, a module is a file containing Python definitions and statements. The file name is the module name with the suffix `.py` appended \(every .py file is a module\). Within a module, the module’s name \(as a string\) is available as the value of the global variable `__name__`.

### Using Modules

* First, we import the module. We will learn more coming up. 
* After the module is imported we can begin utilizing the module's objects. 
* When a module is imported normally, the module will be on it's own namespace. 
  * Thus we need to use dot notation to access the modules objects

```python
import triangle
triangle.start()
triangle.triangle_number(10)
triangle.divisors(10)
triangle.divisor_count_to_find = 100

triangle.start()
# 576 76576500.0 112 73920.0
```

### Importing Modules

There are many ways to import modules. The most common way is to import the module simply using the **import** keyword alone. These modules are imported from the same dir as your program. This method prevents collisions by putting the modules objects into it's own namespace.

```python
# Most common, clean way to do it. Prevents collisions. 
import triangle
triangle.method # Call method
```

By default, you cannot import modules from other dirs. You must place your modules in the same dir as your program unless you use _sys.path_ to modify your Python path at runtime. In short, your Python path is where Python searches by default for modules... aside from your current dir.

**To add a location to your Python path and runtime:**

```python
import sys
sys.path.insert(0, '/path/to/application/app/folder')

import file
```

There are other methods as well. We can give our modules **aliases**

```python
# Same as above except we gave triangle an alias
import triangle as tri
tri.method
```

We can also import specific modules without throwing them into a namespace.

```python
from triangle import divisor_count_to_find, triangle_number

print divisor_count_to_find # output 500
triangle_number(5)
```

We can take the previous example a step further and implement aliases. This will allow us to change the names up to prevent collisons.

```python
from triangle import divisor_count_to_find as dcf, triangle_number as tn

print dcf # output 500
tn(5)
```

Lastly, we can also import an entire module without a namespace. The **\*** tells Python to import all modules without a namespace. This is a dangerous method and should only be used if you are sure there will not be collisions.

```python
from triangle import *
```

### Reference: [Modules](https://docs.python.org/2.7/tutorial/modules.html)

---

|[Next Topic](/05_oop/02_packages.md)|
|---|
