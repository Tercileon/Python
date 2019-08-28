|[Table of Contents](/00-Table-of-Contents.md)|
|---|

---

## Tuples, range & buffer

**Tuples**

Tuples are very similar to lists. The major difference is that tuples are **IMMUTABLE!** So just like strings and numbers, you cannot modify it's contents without reassigning. This also means that the length of tuples are set in stone. Parentheses \(round brackets like these\) are commonly used to declare tuples. But unlike lists, the parentheses are not required! You can declare tuples by just using commas.

```python
# common method to declare tuples
>>> someTuple = (1,2,3,4,5)
# alternative method
>>> neatTuple = 1,2,3,4,5

>>> print neatTuple
(1, 2, 3, 4, 5)

# What does the below do?
>>> del someTuple[2]
```

### Why Use Tuples?

Tuples are still sequence objects. You can still:​

* Implement all common sequence operations​
* Slice​
* Index​

**Useful for:**​

* Returning multiple results from functions​
* Since they are immutable, they can be used as keys for a dictionary.​

## range\(\)
Python 3's range() is essentially a combination of Python 2's range() and xrange() so luckily in Python 3 we only need to worry about using range(). We will mention xrange() so you have some exposure to it and are aware of its existence. 

range() represents an immutable iterable object that always takes the small and same amount of memory irrespective of the size of range because it only stores start, stop, and step values and calculates values as needed.

#### Syntax

**range**_\(stop\)_ **range**_\(start, stop,\[ step\]\)_

_**start:**_ Required when full syntax is used. An integer specifying start value for the range.

_**stop:**_ Required. The boundary value for the range.

_**step:**_ Optional. Step value.

```python

>>> range(4)
range(0,4)

# if we want to see what is contained within our range
>>> list(range(4))
[0, 1, 2, 3]

>>> list(range(2,6))
[2, 3, 4, 5]

>>> list(range(0,50,5))
[0, 5, 10, 15, 20, 25, 30, 35, 40, 45]

>>> list(range(4,12,3))
# ???

>>> list(range(0,-10,-2))
# ???
```
We will cover range() more in depth and use it a lot more when we get to loops.

## xrange\(\)

xrange\(\) is from Python 2 and is similar to range\(\), returns xrange object \(sequence object\) instead of list. Intended to be a simple, efficient \(uses less resources due to one-at-time loading method vs loading all increments\) and a fast way to iterate through a range. In most cases, xrange\(\) will be the way to go. The only time you should use range\(\) is when you are going to be iterating over the list multiple times. This is because xrange\(\) will use more processing power over the length of the repeated iteration vs range... which will return a list and that list will stay and can be referenced whenever.


```python
>>> for i in xrange(10):
>>>    print i
0
1
2
3
4
5
6
7
8
9

# Only even numbers
>>> for i in xrange(2, 10, 2):
>>>     print i
2
4
6
8

# Negative numbers
>>> for i in xrange(-1, -10, -1):
>>>     print i
-1
-2
-3
-4
-5
-6
-7
-8
-9
```

## Buffer \(memoryview\)

Buffer \(memoryview\) is useful if you don’t want to or can’t hold multiple copies of data in memory. It can also be lightning fast since it's not copying the data. Buffer \(or memoryview\) essentially expose \(by reference\) raw byte arrays to other Python objects. That means the argument passed must be in bytes \(ints representing bytes\).

```python
# Python 2
>>> x = b'100'
>>> buffer(x)
<read-only buffer for 0x10b1acc60, size -1, offset 0 at 0x10b1a9930>

# Python 3
>>> x = b'100'
>>> memoryview(x)
<memory at 0x1040b1948>
```

### Practical Example

Below is a great example displaying how much resources and time buffer\(memoryview\) can save you. Copy, paste and run the code yourself. The first set of prints will be normal... the second will be using memoryview. Notice the amount of time it takes to complete each set of operations in bytes vs memoryview. While that may seem small... when more data is being manipulated, the time increases exponentially. A quick example can be found by running the same code below, but moving the prints into the while loops.

```python
import time
for n in (100000, 200000, 300000, 400000):
    data = 'x'*n                            # set data = 'x'*n (if n were 5, xxxxxx)
    start = time.time()                     # start a timer
    b = data                                # set b = data
    while b:                                # remove one x and reasign to b, continue until 0
        b = b[1:]
    print 'bytes', n, time.time()-start     # stop time, print out time it took to do operation


# Same thing here, except we use memoryview instead
for n in (100000, 200000, 300000, 400000):
    data = 'x'*n
    start = time.time()
    b = memoryview(data)
    while b:
        b = b[1:]
    print 'memoryview', n, time.time()-start
```  

---

|[Next Topic](/02_Data_Types/07_mapping.md)|
|---|
