|[Return to Table of Contents](/00-Table-of-Contents.md)|
|---|

---

## Bytes and Bytearray

**Bytes\(\)**

It's worth re-mentioning that Python 2 and Python 3 have differences when it comes to bytes and strings. Python 2 strings are bytes naturally whereas Python 3 is unicode and needs to be defined as bytes when you want to use bytes type. Here are a couple ways to turn Python 3 strings and such.. into bytes. This functionality is backwards compatible with Python 2. It's highly recommended you define Python 2 strings the same way if you are going to be modifying the bytes. Even though it doesn't do anything in Python 2... it will make the job of refactoring code easier, if you had to up Python version to 3.x.


```python
# Method 1 (shortest)
>>> x = b'hello world'
>>> print(x[1])
101 # ASCII dec value

# Method 2 (clean)
>>> x = 'hello world'
>>> y = bytes(x, 'ascii')
>>> print(y)
b'hello world'
>>> print(y[1])
101 # ASCII dec value

# python 2
>>> x = 'hello world'
>>> print ord(x[1]) 
# ord is the inverse of chr()... returns int representing the unicode code point of the argument
101 # Unicode dec value
```

**This can go both ways. We can convert these integer representations back into Unicode or ASCII strings.**

```python
# Python 2 back to ascii string
>>> x = ord('e')
>>> x
101
>>> y = chr(x)
>>> y
'e'
# convert y into a unicode string (this only works in Python 2 because unicode is default in Python 3)
>>> y = unichr(x)
>>> y
u'e'

# Python 3 back to native unicode string
>>> x = ord('e')
>>> x
101
>>> y = chr(x)
>>> y
'e'
# y is now a unicode string... but how do we turn it into a byte/ascii string?
>>> y = bytes(y, 'ascii')
>>> y
b'e'
# Now y is a python 2 str type... bytes/ascii
```

---
## Bytearray\(\)

**Bytearray\(\)** is a mutable sequence of integers in range of 0 &lt;= x &lt; 256; available in Python 2.6 and later​. Byte Arrays are useful when you need to modify individual bytes in a sequence. Since bytearray\(\) takes in a byte/ASCII string... there is a difference in how we must implement this function between Python 2 and 3.

**Python 2**

Python 2 strings, as noted above, are already byte/ascii strings. So all we have to do is pass it through as is. But remember, it's good practice to declare bytes; even in Python 2. \(For this example, I will declare it for demonstration\)

```python
>>> x = "I am a string"
>>> b = bytearray()
>>> b.extend(x) 
# This was done on purpose to show it is mutable 
# You can pass the str directly into the bytearray() function to cut 2 lines
>>> b
bytearray(b'I am a string')
>>> b[2]
97 # decimal for 'a' char
>>> b[2] = 85 # Modifying a byte
>>> b
bytearray(b'I Um a string')​ # notice b did change without reassignment
```

**Python 3**

Python 3 strings on the other hand need to be converted before you can pass them as an argument into bytearray\(\).

```python
>>> b = bytearray(b"I am a string")
>>> b
bytearray(b'I am a string')
>>> b[2]
97 # decimal for 'a' char
>>> b[2] = 85
b
bytearray(b'I Um a string')
```  

---
**Continue to Performance Lab** 2G

---

|[Lab 2G](/02_Data_Types/lab2g.md)|
|---|
