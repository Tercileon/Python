<a href="https://github.com/CyberTrainingUSAF/07-Python-Programming/blob/master/00-Table-of-Contents.md" rel="Return to TOC"> Return to TOC </a>

# Operators

## Comparison Operators

* **x == y**
  * if x equals y, return True​
* **x != y**
  * if x is not y, return True​
* **x &gt; y**
  * if x is greater than y, return True​
* **x &lt; y**
  * if x is less than y, return True​
* **x &gt;= y**
  * if x is greater or equal to y, return True​
* **x &lt;= y**
  * if x is less or equal to y, return True

**Example:**

```python
a=7
b=4

print('a > b is',a>b)

print('a < b is',a<b)

print('a == b is',a==b)

print('a != b is',a!=b)

print('a >= b is',a>=b)

print('a <= b is',a<=b)


#Output
a > b is True
a < b is False
a == b is False
a != b is True
a >= b is True
a <= b is False
```

## Membership Operators

* **in**
  * Evaluates to True if it finds a variable in the checked sequence
* **not in**
  * Evaluates to True if it does not find a variable in the checked sequence

## Identity Operators

* **is**
  * Evaluates to True if variables on either side of the operator point to the same object 
* **is not**
  * Evaluates to True if the variables on either side of the operator does not point to the same object

## Boolean Operators

* **and**
  * Evaluates True if expressions on both sides of the operator are True. 
* **or**
  * Evaluates True if expressions on either side of the operator are True.

**Examples:**

```python
# Example using bitwise operators
a=7
b=4

# Result: a and b is 4
print('a and b is',a and b)

# Result: a or b is 7
print('a or b is',a or b)

# Result: not a is False
print('not a is',not a)

#Output
a and b is 4
a or b is 7
not a is False



# Example using 'in' operator
list1=[1,2,3,4,5]
list2=[6,7,8,9]
for item in list1:
    if item in list2:
        print("overlapping")      
else:
    print("not overlapping")

# Output: not overlapping


# Example of 'is' identity operator
x = 5
if (type(x) is int):
    print ("true")
else:
    print ("false")

# Output: true
```

## Assignment Operators

| Operator | Example | Similar |
| :---: | :---: | :---: |
| = | x = 8 | x = 8 |
| += | x += 8 | x = x + 8 |
| -= | x -= 8 | x = x - 8 |
| \*= | x \*= 8 | x = x \* 8 |
| /= | x /= 8 | x = x/8 |
| %= | x %= 8 | x = x%8 |
| \*\*= | x \*\*= 8 | x = x\*\*8 |
| &= | x &= 8 | x = x & 8 |
| \|= | x \|= 8 | x = x\|8 |
| ^= | x ^= 8 | x = x ^ 8 |
| &lt;&lt;= | x &lt;&lt;= 8 | x = x &lt;&lt; 8 |
| &gt;&gt;= | x &gt;&gt;= 8 | x = x &gt;&gt; 8 |

---

<a href="https://github.com/CyberTrainingUSAF/07-Python-Programming/blob/master/03_Flow_Control/02_io_print.md" rel="Continue to Next Topci"> Continue to Next Topic </a>
