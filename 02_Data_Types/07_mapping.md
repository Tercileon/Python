|[Return to Table of Contents](/00-Table-of-Contents.md)|
|---|

---

## Dictionaries and Sets

### Mapping Types

**Dictionary**

Dictionaries **are mutable** objects and consist of key-value mappings. \(ex: {key: ‘value’, key: ‘value’} \). They are initialized using the curly-brackets {}. Dictionaries are not ordered and support all value types.

```python
>>> my_dict = {} # create empty dictionary​
>>> my_dict['one'] = 1 # add item to the dictionary​
>>> print my_dict
{'one': 1}​

# OR
>>> my_dict = {'one' : 1} #create a dictionary with an item​
>>> print my_dict​
{'one': 1}​
​
>>> my_dict['two'] = 2 # add item to the dictionary​
>>> print my_dict​
{'one': 1, 'two': 2}​

# Grabbing by key
>>> new_dict = {'key1':'value1','key2':'value2','key3':'value3'}
>>> print new_dict['key2']
'value2'
```

**Multi-Dimensional Dictionaries**

Just like lists... Dictionaries can be nested as well to create a multi-dimensional dictionary.

```python
# Dict -> Dict
>>> my_dict = {'key1':{'nestedkey1':{'subnestedkey1':'subnestedValue'}}}
>>> print my_dict
{'key1':{'nestedkey1':{'subnestedkey1':'subnestedValue'}}}

# Grab key 1's value
>>> print my_dict['key1']
{'nestedkey1': {'subnestedkey1': 'subnestedValue'}}

# Grab nested key 1's value
>>> print my_dict['key1']['nestedkey1']
{'subnestedkey1': 'subnestedValue'}

# Grab subnested key 1's value
>>> print my_dict['key1']['nestedkey1']['subnestedkey1']
subnestedValue
```

#### Common Dictionary Operations

```python
>>> d[i] = y # value of I is replaced by y​
>>> d.keys() # grabs all keys
>>> d.values() # grabs all values
>>> d.clear() # removes all items​
>>> d.copy() # creates a shallow copy of dict_x​
>>> d.fromkeys(S[,v]) # new dict from key, values​
>>> d.get(k[,v]) # returns dict_x[k] or v​
>>> d.items() # list of tuples of (key,value) pairs​
>>> d.iteritems() # iterator over (key,value) items​
>>> d.iterkeys() # iterator over keys of d​
>>> d.itervalues() # iterator over values of d​
>>> d.pop(k[,v]) # remove/return specified (key,value)​
>>> d.popitem() # remove/return arbitrary (key,value)​
>>> d.update(E, **F) # update d with (key,values) from E​​
```

## Set and Frozenset

A set is an unordered collection of unique elements. Sets **are mutable** but contain no hash value-- so they can't be used as dict keys or as an element of another set.

```python
>>> new_set = set() # create an empty set​
>>> new_set = {0, 1, 1, 1, 2, 3, 4} ​
>>> new_set​
{0, 1, 2, 3, 4}​

>>> new_set.add(5) # Add new key to set​
>>> new_set​
{0, 1, 2, 3, 4, 5}​

>>> x_set = set("This is a set")​
>>> x_set​
{'s', 't', 'e', 'h', 'I', ' ', 'T', 'a'}​

>>> another_set = set(['Ford', 'Chevy', 'Dodge', 105, 555])​
{'Chevy', 105, 155, 'Ford', 'Dodge'} # many ways to create set​
```

#### Frozenset

Frozensets are identical to sets aside from the fact that they **are immutable**. Since frozensets are immutable, they are hashable as well. So they can be used as a dict key or element of another set.

```python
>>> new_set = frozenset([1,2,2,2,3,4])# create an frozenset​
>>> new_set​
frozenset({1, 2, 3, 4})​
>>> new_set.add(5)​
.......AttributeError: ‘frozenset’ object has no attribute ‘add’​
# Doesn't work since Frozenset is immutable

# Many… many ways to create frozenset as well. ​
​
```

#### Common Set Operations

Some do not apply to Frozenset.

```python
>>> s.issubset(t) # test if elements in s are in t​
>>> s.issuperset(t) # test if elements in t are in s​
>>> s.union(t) # new set with elements of t and s​
>>> s.intersection(t) # new set with common elements​
>>> s.difference(t) # new set with elements in s but not t​
>>> s.symmetric_difference # xor​
>>> s.copy() # new shallow copy of s​
>>> s.update(t) # return set s with elements from t​
>>> s.intersection_update(t)​
>>> s.difference_update(t)​
>>> s.symmetric_difference_update(t)​
>>> s.add(x) # add x to set s​
>>> s.remove(x) # remove x from set s​
>>> s.discard(x) # remove x from set s if present​
>>> s.pop() # remove arbitrary item​
>>> s.clear() #remove all elements from set a​
```

## Additional Functionality

### Conversion Functions

Below are some functions to convert a variable to another type.

```python
>>> int()​
>>> long()​
>>> float()​
>>> complex()​
>>> str()​
>>> repr()​
>>> eval()​
>>> tuple()​
>>> list()​
>>> set()​
>>> dict()​
>>> frozenset()​
>>> chr()​
>>> unichr()​
>>> ord()​
>>> hex()​
>>> oct()​
>>> bin()
```

### Import Sys

Sys is a large module from the Standard Library that contains very useful code and functionality. We will get into what modules are and how to import and such later in the course. For now, we are going to focus on one function from the module.

sys.getsizeof\(object\) --gets the size of the object passed in bytes. As you can imagine, this is going to be very helpful in streamlining your code.

**Documentation:**

* [https://docs.python.org/2.7/library/sys.html](https://docs.python.org/2.7/library/sys.html)​
* [https://docs.python.org/3.6/library/sys.html](https://docs.python.org/3.6/library/sys.html)

#### Example:

```python
>>> import sys​
>>> x = 40​
>>> sys.getsizeof(x)​
12​
```  

**Continue to Performance Lab:** 2H

---

|[Lab 2H](/02_Data_Types/lab2h.md)|
|---|
