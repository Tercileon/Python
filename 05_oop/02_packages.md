|[Return to Table of Contents](/00-Table-of-Contents.md)|
|---|

---

## Packages

Packages are a way to structure Python's module namespace. Essentially a package is just a collection of modules. A module named `__init__.py` is required to treat the directory as a package; allowing the package to be imported the same way a module can be imported. This file can contain initialization code... but it's often best to leave it blank.

### Package Structure

```python
/                       # Top directory
    math_stuff/         # Package
        __init__.py     # special file
        fib.py          # fib module 
        triangle.py     # triangle module 
        Calculator.py   # calculator class module
    more_math_stuff/    # additional package 
        __init__.py 
        other_modules.py
```

### How to Import From a Package

So let's take the package below and walk through an import.

```python
/                       # Top directory
    math_stuff/         # Package
        __init__.py     # special file
        fib.py          # fib module 
        triangle.py     # triangle module 
        Calculator.py   # calculator class module
    more_math_stuff/    # additional package 
        __init__.py 
        other_modules.py # import and run this file (module)
```

**There are two ways we can go about this:**

```python
import more_math_stuff.other_modules

more_math_stuff.other_modules.do_something()
```

**OR**

```python
from more_math_stuff import other_modules as om

om.do_something()
```

Notice the calls to the module. They do behave differently. You can also import the entire package as well.

[More on Packages](https://realpython.com/python-modules-packages/#python-packages)

### Useful Commands

* **dir\(\)**
  * Returns list of names in current local scope or **with argument,** attempts to return a list of valid attributes for object
* **help\(\)**
  * Invokes built-in help system

```python
# dir
>>> print dir()
['__builtins__', '__doc__', '__name__', '__package__']
>>> import(struct)
>>> print dir()
['__builtins__', '__doc__', '__name__', '__package__', 'struct']
>>> print dir(struct)
['Struct', '__builtins__', '__doc__', '__file__', '__name__', '__package__', '_clearcache', 'calcsize', 'error', 'pack', 'pack_into', 'unpack', 'unpack_from']

# help
print help(struct)
# Try it
print help()
# Try it
```  

---

**Continue to Performance Lab:** 5A  

|[Lab 5A](/05_oop/lab5a.md)|
|---|
