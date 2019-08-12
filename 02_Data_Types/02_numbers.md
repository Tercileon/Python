|[Return to Table of Contents](/00-Table-of-Contents.md)|
|---|

---

## Numbers

### Prefixes

Prefixes convert types like **binary, hex and octal** into int.

* No prefix for decimal​
* Prefix with **0b**, b for binary \(ex. 0b10 == 2\)​
* Prefix with **0x**, x for hex \(ex. 0xF == 15\)​
* Prefix with **0o**, o for octal \(ex. 0o100 == 64\)​

```text
$ py -3
>>> 0b10
2

>>> 0xF
15

>>> 0o100
64

>>> x = 0xF
>>> type(x)
<class 'int'>

>>> x
15
```

## Types

* **int \(integer\)**
  * Equivalent to C-Longs in Python 2 and non-limited in Python 3
* **Long**
  * Long integers of non-limited length. Exist only in Python 2
* **Float \(decimal, hex, octal\)**
  * Floating point numbers. Equivalent to C-Doubles
* **Complex**

  * suffix is j or J
  * There are several built-in accessors and functions to act on complex numbers
    * We will not be going over these
  * Complex numbers, ex:

  ```python
  x = 1.5 + 5j
  y = 2
  z = x + y
  print(z)
  #Output: (3.5+5j)

  z = z + 3j
  print(z)
  #Output: (3.5+8j)
  ```

### Numbers are IMMUTABLE!

Numbers cannot be modified in place. Be sure to either reassign your current variable or assign the number to a new variable.

```bash
$ py -3

>>> x = 10
>>> print(x)
10

>>> x = 15
>>> print(x)
15

>>> x = x + 5
>>> print(x)
20

>>> x + 5
25

>>> print(x)
20
```

## Bool \(True or False\)

Bools are a subclass of int. This was done around Python 2.2 to allow previous implementations of bools \(0 and 1\) to continue working… especially so with C code that utilizes Pylint\_Check\(\)

#### Truth Value Testing

* The following will evaluate to False:
  * False
  * zero numeric type- 0 0.0 0
  * None
  * empty sequence – ‘’ \(\) \[\]
  * empty mapping- {}
  * instances of user defined classes \(will get into later\)​
* The following will evaluate to True: Everything else, not limited to but including–
  * True, 1
  * any number that is less than or greater than 0... but not 0
  * non-empty sequence/mapping, etc

## Operators

There are some more differences between Python and many other languages that need to be brought to light. Increment operators **\(x++, y--, etc\)** do not exist in Python. To increment in Python, **you can use shorthand: a += 1, x -= 5, z \*= 2, etc**

| Operator | Description | Example | Result |
| :--- | :--- | :--- | :--- |
| + | Addition | 4 + 5 | 9 |
| - | Subtraction | 10 - 5 | 5 |
| \* | Multiplication | 4 \* 2 | 8 |
| / | Division\* | 3 / 2 | Py2\(1\) Py3\(1.5\) |
| // | Floor Division | 3.0 // 1.0 | 1 \(~int division\) |
| % | Modulus \(remainder\) | 4 % 2 | 0 |
| \*\* | Exponentiation | 4 \*\* 2 | 16 |

**\*3.0 / 2 will return 1.5 for both Python 2 and Python 3**

* We are already familiar with what modulus does... it gives us the remainder. 
* Floor division on the other hand is the equivalent of dividing 2 whole numbers that should have a remainder... in Python 2.
  * Remember, Python 2 will truncate the remainder unless you specify one of the types as float. 
  * Floor division will always take the floor... or the lowest number. It does not round up. 

## Bitwise Operators

* Ahh, the dreaded bitwise operators are back! 
* Bitwise Operators directly manipulate bits. There really is no speed advantage to bitwise operators in Python. The main advantage of bitwise operators is for scripting, compression, encryption, communication over sockets \(checksums, stop bits, control algorithms, etc\).

| Operator | Description | Example | Result |
| :--- | :--- | :--- | :--- |
| & | Binary AND | 1 & 3 | 0001 & 0011 == 0001 \(1\) |
| \| | Binary OR | 1 \| 3 | 0001 \| 0011 == 0011 \(3\) |
| ^ | Binary XOR | 1 ^ 3 | 0001 ^  0011 == 0010 \(2\) |
| ~ | Binary Ones Complement | ~3 | ~00000011 == 11111100 |
| &lt;&lt; | Binary Left Shift | 1 &lt;&lt; 3 | 00000001 &lt;&lt; 3 == 00001000 |
| &gt;&gt; | Binary Right Shift | 1 &gt;&gt; 3 | 00000001 &gt;&gt; 3 == 00000000 |

### Order of Operations

| Operation | Precedence | Extra |
| :--- | :--- | :--- |
| \(\) | 1 | Anything in brackets is first |
| \*\* | 2 | Exponentiation |
| -x, +x | 3 | N/A |
| \*, /, %, // | 4 | Will evaluate left to right |
| +, - | 5 | Will Evaluate left to right |
| &lt;, &gt;, &lt;=, &gt;=, !=, == | 6 | Relational Operators |
| Logical Not | 7 | N/A |
| Logical And | 8 | N/A |
| Logical Or | 9 | N/A |

### Type Conversion

```python
# int(x, base)
## Returns x as 'base' integer​. 'base' specifies base if x is string, otherwise opitional
### EXAMPLE 1
x = 10.5
int(x)
# output: 10

### EXAMPLE 2
y = "101101"
int(y, 2) # specifiy y as a base 2 
# output: 45

#########################

# float(x)
## Returns x as a float
x = 30
float(x)
# output: 30.0

#########################

# complex(real, imag)
## Returns complex number, defaults for real/imag is 0

complex(2, -3)
# output: (2-3j)

complex(2, 3)
# output: (2+3j)

#########################

# chr(x)
## Returns string of one character for x as ASCII
x = 10
chr(x)
# output: '\n'

x = 10.5
chr(int(x)) # notice what we did here? 
# output: '\n'

#########################

# ord(x)
## Returns ASCII value for x as string of one char
ord('\n') # notice what we did here?
# output: 10

#########################

# hex(x)
## Returns x as hex value
hex(10)
# output: '0xa' 
## Notice how the output is a string, there is no hex type

#########################

# oct(x)
## Returns x as octal
oct(10)
# output: '012'
## Same thing here

#########################

# bin(x)
## Returns x as binary
bin(10)
# output: '0b1010'
## Same thing here
```

_There are some differences between Python 2 and Python 3 numbers. The biggest difference being the removal of the Long Type in Python 3._  

---

**Continue to Performance Labs:** 2B and 2C

---

|[Lab 2B & 2C](/02_Data_Types/lab2b_c.md)|
|---|
