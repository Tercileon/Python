<a href="https://github.com/CyberTrainingUSAF/07-Python-Programming/blob/master/00-Table-of-Contents.md" rel="Return to TOC"> Return to TOC </a>

# User Classes Pt2

## Encapsulation in Python

In C++ and other languages, encapsulation is harped on pretty hard and the languages give you features that really allow for such a mechanism. In Python? Not so much. Well, not to the level of which we are used to.

### Public

All member variables and methods are public by default in Python. Just do as you do if you want public.

### "Protected"

A protected member \(in C++ and Java\) is accessible **only** from within the class and it’s subclasses. In C++, we can create idiot-proof ways to really protect things members. In Python? Well, it's more of a suggestion. By prefixing the name of your member with **a single underscore**, you’re telling others “don’t touch this, unless you’re a subclass”. And by others... we mean other programmers. Yes, you can still access the members outside of the class.

```python
class Example:
    def __init__(self, name):
        self.name = name
        self._number = None # "protected" variable
        self._displayName()

    def _displayName(self):
        print "Hello, {}".format(self.name)

    def setNumber(self, num):
        self._number = num

    def getNumber(self):
        return self._number

print "====Proper Things====\n"
a = Example("Will")
a.setNumber(21012345678)
print a.name
print a.getNumber()


print "====Does it really work?====\n"
print a._number
a._displayName()
```

### "Private"

Same thing really applies here. By declaring your data member private you mean, that nobody **should** be able to access it from outside the class. Python supports a technique called _name mangling_. This feature turns every member name **prefixed with at least two underscores and suffixed with at most one underscore** into `_<className><memberName>`

```python
class Example:
    def __init__(self, name):
        self.name = name
        self.__number = None # "private" variable
        self.__displayName()

    # private method
    def __displayName(self):
        print "Hello, {}".format(self.name)

    def setNumber(self, num):
        self.__number = num

    def getNumber(self):
        return self.__number

print "====Proper Things====\n"
a = Example("Will")
a.setNumber(21012345678)
print a.name
print a.getNumber()

print "====How to get around it====\n"
print a._Example__number    # This works, though it is much more confusing and even throws errors
```

#### Python Specific Breakdown

```text
__init__ (Constructor)
__del__ (Deconstructor)
```

* It's best to name the Python file after the class name/vise-versa.
* `class ClassName(object):` -- to define class
* Name classes using CapWords convention \(camel-case\)
* Variables defined under classes are shared though all instances
* Variables defined in methods using `self` are only for a single instance
* When creating methods, the first parameter must be self. \(similar to "this" in other languages\)
* A "private" member can be created by prepending a double underscore \(only prepend\) to the name. It will not be visable outside of the class. \_\_example
* Inheritance, multiple inheritance and polymorphism are all supported
* var.attrib = value is the common way to interact\(dot notation\)
* getattr, hasattr, setattr, delattr exist for manipulating attributes as well
* built in: 

```python
__dict__, __doc__, __name__, __module__, __bases__
```

* Overloadable:

```python
__init__, __del__, __repr__, __str__, __cmp__
```

* dir\(\), type\(\), isinstance\(\) are built in functions

#### Creating an Instance in a Different File

```python
from MyClass import MyClass

x = MyClass(name = "Iron Man")
print x.getName()
```

## Composition vs Inheritance

* Best advice is composition over inheritance, but use inheritance when needed. 
* Inheritance can complete things \(especially multiple inheritance\) and make larger projects confusing
* Namespace collisions are a major problem in inheritance
* Time must be given to design to effectively use inheritance, which could be time used used to stand up composition quicker. 

### Inheritance Example

**Parent Class**

```python
class Person(object):
    def __init__(self, name):
        self.__name = name
        self.__age = None
        try:
            firstBlank = self.__name.rindex(' ')
            self.__lastName = self.__name[firstBlank+1:]
        except:
            self.__lastName = None

    def getLastName(self):
        return self.__lastName

    def setAge(self, age):
        self.__age = age

    def getAge(self):
        if age == None:
            return "N/A"
        else: 
            return self.__age
```

**Child Class**

```python
from Person import Person

class USResident(Person):
    """A person who resides in the US"""

    def __init__(self, name, status):
        Person.__init__(self, name)

        if status.lower() != 'citizen' and /
        status.lower() != 'legal_resident' and /
        status.lower() != 'illegal_resident':
            raise ValueError()
        else:
            self.__status = status

    def getStatus(self):
        """
        Returns the status
        """
        return self.__status
```

**Example Call**

```python
from USResident import USResident

resident = USResident("Joe Smo", "citizen")
resident.setAge(23)

print "{} is a {} and is {} years of age.".format(resident.getLastName(), resident.getStatus(), resident.getAge())
```

### Composition Example

```python
class Engine:

    def __init__(self, size, amount):
        self.size = size
        self.amount = amount

    def calculatePower(self):
        return self.size * self.amount

class Payload:

    def __init__(self, name, typeOf, weight):
        self.name = name
        self.typeOf = typeOf
        self.weight = weight

    def neededPower(self):
        return self.weight * .25

class AtlasRocket:

    def __init__(self, size, amount, name, typeOf, weight):
        self.Engine = Engine(size, amount)
        self.Payload = Payload(name, typeOf, weight)

    def missionCapable(self):
        power = self.Engine.calculatePower()
        neededPower = self.Payload.neededPower()

        if power > neededPower:
            return True
        else:
            return False

    def printMissionStats(self):
        print "Avaliable power: {}".format(self.Engine.calculatePower())
        print "Needed Power: {}".format(self.Payload.neededPower())


atlasV = AtlasRocket(200, 4, "DSCS", "COMM", 2000)

if atlasV.missionCapable() == True:
    print "Mission is a go"
    atlasV.printMissionStats()
else:
    print "Mission is not a go"
    atlasV.printMissionStats()
```

### Function vs Method

A **function** is a piece of code that is called by name. It can be passed data to operate on \(i.e., the parameters\) and can optionally return data \(the return value\). All data that is passed to a function is explicitly passed.

```text
def sum(num1, num2):
    return num1 + num2
```

A **method** is a piece of code that is called by name that is associated with an object. In most respects it is identical to a function except for two key differences.

1. It is implicitly passed for the object for which it was called.
2. It is able to operate on data that is contained within the class \(remembering that an object is an instance of a class - the class is the definition, the object is an instance of that data\).

```text
class Dog:
    def my_method(self):
        print "I am a Dog"

dog = Dog()
dog.my_method()  # Prints "I am a Dog"
```

## More Material

* [PyDocs](https://docs.python.org/2.7/tutorial/classes.html)
* [Python Textbook Docs](https://python-textbok.readthedocs.io/en/1.0/Classes.html)
* [Composition and Inheritance](http://blog.thedigitalcatonline.com/blog/2014/08/20/python-3-oop-part-3-delegation-composition-and-inheritance/)  

---
## Continue to Lab 5C

<a href="https://github.com/CyberTrainingUSAF/07-Python-Programming/blob/master/05_oop/lab5c.md" > Continue to Lab 5C </a>
