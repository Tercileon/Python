|[Table of Contents](/00-Table-of-Contents.md)|
|---|

---

## User Classes Pt1

Classes are used to create objects that bundle data and functionality together. With this, classes are highly reusable, cleaner and more efficient. In other languages, some entites are objects and some are not. In Python, everything is an object. Classes and built-in types were at one point different. But that has all since been merged and both are now objects of type **type**. \(more to come on this later\) Here are some considerations:

### **Keywords**

Reserved words of the language, and cannot be used as ordinary identifiers. Do not use any of these for any naming. They must be spelled exactly as written here:

```text
and       del       from      not       while    
as        elif      global    or        with     
assert    else      if        pass      yield    
break     except    import    print     
class     exec      in        raise              
continue  finally   is        return             
def       for       lambda    try
```

To verify that a string is a keyword you can use [`keyword.iskeyword`](https://docs.python.org/3/library/keyword.html#keyword.iskeyword); to get the list of reserved keywords you can use [`keyword.kwlist`](https://docs.python.org/3/library/keyword.html#keyword.kwlist):

```text
>>> import keyword
>>> keyword.iskeyword('break')
True
>>> keyword.kwlist
['False', 'None', 'True', 'and', 'as', 'assert', 'break', 'class', 'continue', 'def', 
 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 
 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 
 'while', 'with', 'yield']
```

### Creating a Class

Let's take a quick look at an example of a class, using the famous Person example. This example is very basic and will be expanded upon as we go.

```python
# This is the class
class Person:
    """Stage 1 of Person Class

    We will expand on this."""

    firstName = "James"
    lastName = "Bond"
    birthday = "08/21/1800"
    age = "200"
    email = "someEmail@email.com"

    def f(self):
        return "This is the Person class"

# This is the instantiation of class Person as object x
x = Person()

# This is using object x
print x.f()
print "This person's name is: {} {}".format(x.firstName, x.lastName)

# We can also do this...
print Person.firstName
```

Let's take a look at what we have above.

* To create a class, we use the **class keyword** followed by the class name. 
* Notice, the name starts with a capital letter. This is following PEP8 standards.
* Inside the class, we created a multi-line docstring. Generally at least a single line docstring is needed. 
* Below that, we have some **Class Variables:** firstName, lastName, birthday, age and email. These are varibales shared between all instances of a class. 
  * We also have **Instane Variables** which belong only to that instance. These are generally defined within **Methods**.
* Below the class variables, we have a method f. This is the same thing as a member function we are used to in C++. 
* After the creation of the class itself, concepts start to blur between Python and C++. 
  * Notice we call Person\(\) and assign it's value to x. This is called **class instantiation**. This is a concept we should already be used to thanks to C++.
  * x now holds our object, from here we can access all public class variables and methods. In our case, everything is public. 
    * We do just that on the next line, printing x.f\(\). Just like C++, we use dot-notation to access class variables and methods. 
    * x.f\(\) calls the f\(\) method of class Person, object x. 
    * We then access class variables firstName and lastName on the next line and print them out. 
  * Finally, the last line. Notice we don't access object x, instead we access the class directly. Remember, even class creation and types are objects. So what does this mean?
    * We have something called **attribute references** in Python. 
    * This allows us to access a classes attributes... meaning, we can modify things on the class level, even after instances are created. Changes are displayed across the board on all instances only if the instance's variable wasn't modified first. If it was, that variable no longer shares a connection with the class and becomes a sole instance variable. Let's take a look at an example in the interactive terminal. 

```python
>>> class someClass:
...     x = 100
...
>>> someClass.x
100
>>> someInstance = someClass()
>>> someInstance.x
100
>>> someClass.x = 400
>>> someInstance.x
400
>>> someInstance.x = 1000
>>> someInstance.x
1000
>>> someClass.x = 0
>>> someInstance.x
1000
```

So as we have seen above, despite it being a basic example of a class, it already seems very useful. But classes get much better in Python. Let's cover some other class concepts.

### `__init__()`

It is possible to create objects with instances customized to a specific state. Just like C++, we have the ability to construct objects. But we also have the ability to customize objects. These two things are different. `__init__()` is not a constructor. Instead, this comes after the constructor and allows us to customize our object. `__new__()` on the otherhand is the constructor. We will not be going over the use of `__new__()`.

#### `self`

Before we can continue on `__init__()`, we need to understand the word `self`. The `self` in python represents or points the instance which it was called. Remember the difference between **instance variables** and **class variables**? One is tied to only the specific instance and the other is tied to all instances. Well, we went over how to create and modify class variables. We also went over how to convert one to a instance variable. But how do we create instance variables with the intention to do so? That's where self comes in. It's best if we take a look at another Python Interpetor example.

```python
>>> class someClass:
...     ex1 = 0
...     ex2 = 0
...
...     def f(self, val):
...             ex1 = val
...             self.ex2 = val
...
>>> # the class has been created. We also created a method.
... # the method attempts to change ex1 and self.ex2 to val
...
>>> someInstance = someClass()
>>> someInstance.ex1
0
>>> someInstance.ex2
0
>>> someInstance.f(100)
>>> someInstance.ex1
0
>>> someInstance.ex2
100
```

* Notice how we had this method `f()`. 
  * `f()` has two arguments, `self` and `val`. 
  * `self` as we said above, represents the specific instance for which it was called. When the method is called, self is automatically populated by Python. So there is no need for us to pass a self argument. 
  * `val` will be our argument which changes `ex1` and `ex2`
  * Now, let's assume we got rid of this class and converted the class variables to normal global variables and the `f()` method to a regular function. 
    * If we wanted to modify a global variable within a function, we would have to define `global ex1` before acting on `ex1`
    * This concept is kinda the same for `self` within classes... except the scope stops at that of the instance rather than accessing the global. 
  * Once we created our instance and called the `f()` method... we observed it only changed `ex2`. This is because `self` accessed the instance and grabbed it's instance variable rather than creating a new variable within the function scope. 

In short, by using `self`... we are telling Python that we want to modify the classes instance variables rather than create/modify variables local to something else such as a method.

#### Utilizing `__init__()`

Now that we have a general understanding of `self`, let's create a `__init__()` method.

We can do something as simple as:

```python
class X:

    def __init__(self):
        self.i = "yay"

# Invalid
print X.i  # We will get an error, i is not a class variable

# Valid
a = X()
print a.i  # Output will be 'yay'
```

This prevents us from being able to change `data` across all classes. But we have even more flexibility than that in Python, we can also pass additional arguments to `__init__()` via on object instantiation.

```python
def __init__(self, firstName, lastName):
    self.firstName = firstName
    self.lastName = lastName


# Once we go to create the object
x = Person("James", "Bond")
```

Now that we have learned how to utilize `__init__()`... let's update our example.

```python
# This is the class
class Person:
    """Stage 2 of Person Class

    We will expand on this."""

    def __init__(self, firstName, lastName, birthday, age, email):
        self.firstName = firstName
        self.lastName = lastName
        self.birthday = birthday
        self.age = age
        self.email = email

    def printDetails(self):
        print "First Name: {}".format(self.firstName)
        print "First Name: {}".format(self.lastName)
        print "First Name: {}".format(self.birthday)
        print "First Name: {}".format(self.age)
        print "First Name: {}".format(self.email)

# This is the instantiation of class Person as object x
x = Person("James", "Bond", "08/21/1800", 200, "someEmail@email.com")
x.printDetails()
```  

---

**Continue to Performance Lab:** 5B  

|[Lab 5B](/05_oop/lab5b.md)|
|---|
