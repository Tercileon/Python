|[Return to Table of Contents](/00-Table-of-Contents.md)|
|---|

---

## UnitTesting

Unit testing is a development process where parts of small code \(called units\) are individually and independently tested for proper operation. This can of course be done manually... but it is more often automated. This is an extremely important habit to build.

Python offers a powerful built in unit testing module called unittest.

#### References:  [**HitchHiker's Guide**](http://docs.python-guide.org/en/latest/writing/tests/),  [**PyDocs**](https://docs.python.org/2/library/unittest.html)

**Example:**

```python
import unittest

def addx(x):
    return x + 1

class MyTest(unittest.TestCase):
    def test(self):
        # is addX(3) == 4?
        self.assertEqual(addx(3), 4)

# Run test on file launch
if __name__ == '__main__':
    unittest.main()
```

* Above, we define a function in which we want to test... a unit. 
* Then we create a test class and make it a child of **TestCase**
* Then we call upon one of the many assert methods. \([https://docs.python.org/2/library/unittest.html\#assert-methods\)](https://docs.python.org/2/library/unittest.html#assert-methods)

**Output:**

```text
----------------------------------------------------------------------
Ran 1 test in 0.001s

OK
```

In our case, this is exactly what we want to see. But what happens if the test case fails? Let's pass in the argument 4 to addx and see.

```text
F
======================================================================
FAIL: test (__main__.MyTest)
----------------------------------------------------------------------
Traceback (most recent call last):
  File ".\unit_testing.py", line 9, in test
    self.assertEqual(addx(4), 4)
AssertionError: 5 != 4

----------------------------------------------------------------------
Ran 1 test in 0.001s

FAILED (failures=1)
```

* We get a nice fat **F** for failure
* Where the file failed
* The normal traceback
* The AssertionError which breaks down a more readable reason why it failed
* The runtime for each test
* And a **FAILED** status indicating how many failures. 

### Doctest

The doctest module searches for sections of text that look like interactive Python sessions in docstrings, and then executes them to verify that they work.

```python
def addition(x, y):
    """ Return x plus y

    >>> addition(3, 3)
    6
    >>> addition(5, 2)
    1
    """

    return x + y

if __name__ == '__main__':
    import doctest
    doctest.testmod()
```

```text
**********************************************************************
File ".\unit_testing.py", line 6, in __main__.addition
Failed example:
    addition(5, 2)
Expected:
    1
Got:
    7
**********************************************************************
1 items had failures:
   1 of   2 in __main__.addition
***Test Failed*** 1 failures.
PS C:\Users\xconstaud\Documents\Python\re>
```

## Conclusion

As you have guessed, this can be insanly useful. In most cases, spending the extra time unit testing will save you a lot more time over debugging.

---

|[Next Topic](/06_advanced/06_metaclasses.md)
|---|
