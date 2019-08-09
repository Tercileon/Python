|[Return to Table of Contents](/00-Table-of-Contents.md)|
|---|

# PyDocs & PEP8

### PyDoc\(s\)

* **PyDocs** is shorthand for **Python Documentation** and will be your go-to resource for everything Python. It is highly encouraged that you attempt to find the answer using PyDocs before asking an instructor or anyone else a question.
* **Pydoc** is a command that evokes the Python interpreter and utilizes the **help\(\)** function to give you even more detail about a given object. You can also open up the Python interpreter and use help\(object\) _replacing object with the object you want to look up_.
* **help\(\)** is a function that gives you a TON of data. For instance, object methods, module, important information, help, etc.
* Understanding how to use PyDocs, pydoc command and help\(\) function is not only testable... but it's an essential piece in becoming proficient in Python.

**2.7:** [**https://docs.python.org/2.7/**](https://docs.python.org/2.7/)

**3.x:** [**https://docs.python.org/3/**](https://docs.python.org/3/)

### Standard Library

The **Python Standard Library** contains all of the built in functionality of Python; and well, theres a lot of functionality included. The lectures will not even begin to scratch the surface of the Standard Library. With that said, you are encouraged to dive into the library and use whatever you can... whenever you can. You are not limited to just what I teach you. **USE THE LIBRARY!**

**2.7:** [**https://docs.python.org/2.7/library/index.html**](https://docs.python.org/2.7/library/index.html)

**3.x:** [**https://docs.python.org/3.7/library/index.html**](https://docs.python.org/3.7/library/index.html)

#### Pydocs Standard Library Requirments

You are required to look up each and everything we go over, using the PyDocs/pydoc/help\(\), throughout this course. Why? There are lots of functions and methods that can be applied to many different things. I will teach you many things as we go, but it's your responsiblity to ensure you know as much as possible per each topic we go over.

### Styling and PEP8

**PEP8** is shorthand for **Python Enhancement Protocol 8.** Think of this as the bible for Python; the dos and do-nots of formatting and styling. Below are some of the more important commandments.

* Python is **whitespace sensitive!** Unlike C, C++, Java, etc, Python does not use brackets. Instead, Python utilizes an indentation system. 
* **Spaces** are preferred over tabs, you cannot mix. **PEP8** commands 4 spaces per indention level \(tab\). **Using editors with different tab settings may break code!**
* To ensure you do not break your code... **use spaces!** \(You can setup the tab button to output 4 spaces on most major text editors and IDEs\)

### PEP8: [https://www.python.org/dev/peps/pep-0008/](https://www.python.org/dev/peps/pep-0008/)

#### Documenting Code:

Python brings many features we are already familiar with in other programming languages, but gives the user a bit more power in their documentation.

```python
# This is a comment
```

```python
"""This is a single line docstring"""
```

```python
"""This is a multiline 
comment
```

```python
"""This is a multiline docstring

Notice the separation? Let's get into that and explain it. 
"""
```

**What is the difference between Docstrings and Comments?**

* **Docstrings** are targeted towards people who don't need to know how the code works. 
  * Docstrings can be converted directly into actual documentation
  * No implementation details unless they relate to the use
  * Notice the gap in the multiline docstring? 
    * On a multiline docstring, the first line is a short description. This should only be one line. 
    * Second line is left blank to visually separate the summary from the rest of the description.
    * The following lines are used for additional details
* **Comments** are used to explain what, why and how something is going on to other programmers. These are no different than C/C++ aside from syntax.  

## Exercise

* Take a moment to step through PEP8 and and learn the styling and formatting requirments
* Pay most attention to the basics:
  * Indentation
  * Maximum line length
  * The entire comments section
    * Ensure to include a docstring at the top of all of your labs that includes your:
      * name
      * project/lab
      * date
  * Naming Conventions
  * Remember what else in contained within and return to PEP8 as we learn new concepts. You are expected to abide by PEP8 during the class. 

---

|[Next Topic](/01_python_features/03_objects.md)|
|---|
