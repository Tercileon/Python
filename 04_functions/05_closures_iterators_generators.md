|[Table of Contents](/00-Table-of-Contents.md)|
|---|

---

## Closures, Iterators & Generators

### Closures

A Closure is a function object that remembers values in enclosing scopes regardless of whether those scopes are still present in memory. If you have written a function that returned another function, you probably have used closures without even knowing.

**Example:**

```python
def generate_power_func(n):
    def nth_powah(x):
        return x**n
    return nth_powah


x = generate_power_func(10)
print(x)
# What happens? How is this possible?
```

```python
def generate_power_func(n):
    def nth_powah(x):
        return x**n
    return nth_powah


x = generate_power_func(10)
print(x)

y = x(4)
print(y)

# What happens now?
```

### Why Use Closures?

* Closures can avoid the use of global values and provide some form of data hiding. 
* They provide a layer of simplicity

### Why to Avoid Closures?

* They are harder to debug
* They may not always be cleaner
* They can get complex quickly

## Iterators

An iterator is just an object with a state that remembers where it is during iteration, something that can be looped upon. We've gone over some Iterable objects like for loops, strings, lists, dictionaries, etc. Now we will learn how to make our own iterator using iter object.

### Why use Iterators?

Building your own iterator means that you can save memory space. If you have a very large data set you can use iterators for lazy evaluation.

**Example of iter function:**

```python
>>> x = iter([1, 2, 3, 4, 5, 6])
>>> print(x)
<listiterator object at 0x02B2AB30>
x.next()
1
x.next()
2
x.next()
3
x.next()
4
x.next()
5
x.next()
6
x.next()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
StopIteration
```

The one we will be using the most is the range\(\) function. Below is an iterator, implemented as a class that works like range. This is your first major look at classes... don't freak out! Let's break this down.

```python
class yrange:
    def __init__(self, n):
        self.i = 0
        self.n = n

    def __iter__(self):
        return self

    def next(self):
        if self.i < self.n:
            i = self.i
            self.i += 1
            return i
        else:
            raise StopIteration()

# using y range
yrange(3)
y.next()
0
y.next()
1
y.next()
2
y.next()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "<stdin>", line 14, in next
StopIteration
```

As we learned in the Data Types lecture... range\(\) loads one at a time. The yrange\(\) class here does the same thing. There are lists, tuples, etc... loaded up. Instead, we deal with two variables: i and n.

## Generators

Generators are also iterators \(iterators are not always generators though\). Generators simplify the creation of iterators. A generator is simply a function that produces a sequence of values to iterate through rather than a single value.

Before we go over the example lets discuss yield. Yield is similar to return however yield produces a sequence of values. If there is a yield in the body of the function then it is a generator. 

```python
def yrange(n):
    i = 0
    while i < n:
        yield i
        i += 1
my_gen = yrange(10)
print(my_gen)
for i in my_gen:
    print(i)

# output
<generator object yrange at 0x007F3328>
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
```

Taking a look at the code above... we created a sequence object and iterated over it using a for loop.

**Note:** When functions return all state is lost, a yield preserves local state and returns a generator object.

---

|[Next Topic](/05_oop/README.md)|
|---|
