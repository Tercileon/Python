|[Table of Contents](/00-Table-of-Contents.md)|
|---|

---

## OOP Terminology Review 

**Attribute**

* Values associated with an individual object. Attributes are accessed using the 'dot syntax':

```text
a.x means fetch the x attribute from the 'a' object.
```

**Argument**

* A value passed to a function \(or method\) when calling the function. There are two types of arguments:
* _keyword argument_: an argument preceded by an identifier \(e.g. `name=`\) in a function call or passed as a value in a dictionary preceded by `**`. For example, `3` and `5` are both keyword arguments in the following calls to `complex()`:

```text
complex(real=3, imag=5)
complex(**{'real': 3, 'imag': 5})
```

* _positional argument_: an argument that is not a keyword argument. Positional arguments can appear at the beginning of an argument list and/or be passed as elements of an iterable preceded by `*`. For example, `3` and `5` are both positional arguments in the following calls:

```text
complex(3, 5)
complex(*(3, 5))
```

**Class**

* A template for creating user-defined objects. Class definitions normally contain method definitions that operate on instances of the class.
* Classes provide a means of bundling data and functionality together. Creating a new class creates a new type of object, allowing new instances of that type to be made. Each class instance can have attributes attached to it for maintaining its state. Class instances can also have methods \(defined by its class\) for modifying its state.

**Class Variable**

* Variables defined within the class definition that belong to the class. These variables are shared to all instances of the class.

  ```python
  class TestClass:
      i = 10

  print TestClass.i
  ```

**Constructors**

* Fuctions that are automatically called when you create a new instance of a class.

**Conditional Statement**

* Statement that contains an "if" or "if/else".

**Deconstructor**

* Called when an object gets destroyed. It’s the polar opposite of the constructor, which gets called on creation. These methods are only called on creation and destruction of the object. They are not called manually but completely automatic.

**def**

* Defines a function or method

**Debugging**

* The process of finding and removing programming errors.

**Function**

* A parameterized sequence of statements.

### **Syntax**

```text
def function_name(parameters, named_default_parameter=value):
  # Some code here
```

**Function/Method Overloading**

* Function Overloading is the ability to create multiple functions with the same name. This allows us to pass different parameters. In Python, this is generally not needed. Instead... we can set default and optional parameters.

  ```python
  def someFunc(x, y, z = None):
      if z is None:
          # Set a default for z or don't use it
      else:
          # Set and use all three

  someFunc(1,2)
  someFunc(1,2,3)
  ```

**Generator**

* A function which returns an iterator. It looks like a normal function except that it contains [`yield`](https://docs.python.org/2/reference/simple_stmts.html#yield) statements for producing a series of values usable in a for-loop or that can be retrieved one at a time with the [`next()`](https://docs.python.org/2/library/functions.html#next) function.

**Immutable**

* An object with fixed value. Immutable objects include numbers, strings and tuples.

**Inheritance**

* A term used in OOP meaning that classes can inherit from other classes. In other words, it's the transfer of characteristics from one class to another class/classes that are derived from it. 

**Instance**

* An individual object of a certain class. 

**Instance Variable**

* Similar to Class Variables... except they are only accessible to that one instance. These generally start with the 'self' keyword and are contained within methods.

  ```python
  class NameClass:
      def __init__(self, name):
          self.name = name

  dis_class =  NameClass('your_name')
  print dis_class.name
  #OUTPUT:
  'dis_name'
  ```

**Instantiation**

* Instantiation is the act of creating an object instance from a class.

**Lambda**

* A shorthand to create anonymous functions.

**Library**

* A library is used loosely to describe a collection of the core modules.The term ‘standard library‘ in Python language refers to the collection of exact syntax, token and semantics of the Python language which comes bundled with the core Python distribution.

**Method**

* Methods are functions that are called using the attribute notation. There are two flavors: built-in methods \(such as append\(\) on lists\) and class instance methods. A method is similar to a function but is associated with an object.

**Module**

* The basic unit of code reusability in Python. A block of code imported by some other code.

**Namespace**

* A mapping from names to objects. The namespace is a place where a variable is stored in a Python program's memory. Namespaces are implemented as a dictionary. There are the local, global and builtins namespaces and the nested namespaces in objects \(in methods\).

**Nested Scope**

* The ability to refer to a variable in an enclosing definition. For instance, a function defined inside another function can refer to variables in the outer function.

**Object**

* Any data with state \(attributes or value, etc...\) and defined behavior \(methods or functions, etc...\). An object can be assigned to a variable or passed into a function as a argument. It's a unique data structure that's defined by it's type or class, etc... **Everything** in Python is an object. 

**Operator Overloading**

* Operator Overloading is the ability to change the meaning of an operator. This is often done by assigning more than one function to a particular operator.

**Package**

* A directory of Python module\(s\). \(Technically, a package is a Python module with an `__path__` attribute.\)

**Parameter**

* A named entity in a function \(or method\) definition that specifies an argument \(or in some cases, arguments\) that the function can accept.

**Polymorphism**

* The ability to leverage the same interface for different underlying forms such as data typesclasses or functions. This permits  to use entities of different types at different times.

**Self**

* Represents the instance of the class. By using the "_self_" keyword we can access the _attributes_ and _methods_ of the class in python.

**Special Method**

* A method that is called implicitly by Python to execute a certain operation on a type, such as addition. Such methods have names starting and ending with double underscores. Special methods are documented in [Special method names](https://docs.python.org/2/reference/datamodel.html#specialnames).

**Type**

* The type of a Python object determines what kind of object it is; every object has a type. An object’s type is accessible as its [`__class__`](https://docs.python.org/2/library/stdtypes.html#instance.__class__) attribute or can be retrieved with `type(obj)`.

**Variable**

* Placeholder for texts and numbers. The equal sign \(=\) is used to assign values to variables.

### Reference: [Python Glossary](https://docs.python.org/2/glossary.html)  

---
**Continue to Performance Lab:** 5D

---

|[Lab 5D](/05_oop/lab5d.md)|
|---|
