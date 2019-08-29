|[Table of Contents](/00-Table-of-Contents.md)|
|---|

---

## For Loops

### For Loop in C:

```c
char *my_string = "Python";
for (int i = 0; i < strlen(my_string); i++) {
    printf(%c\n", my_string[i]);
}
```

### Python in C Style:

```python
my_string = "Python"
for i in range(len(my_string)):
    print(my_string[i])
```

While the Python one certainly is shorter and looks cleaner... it's still not Pythonic for our use. Though, there will be times where range\(len\(\)\) formula is useful... mostly when dealing with mutable types.

### For Loop... Python Style

```python
my_string = "Python"
for letter in my_string:
    print(letter)
```

So easy, a caveman can do it! But, how does this happen under the hood?

Remember Data Types chapter? Strings are iterable. The "in" operator simply calculates the count of my\_string and iterates through it as var letter. The value of letter is my\_string\[i\].

## For Looping Dictionaries

One way to set up looping for a dictionary

```python
#In python 2 use the method iteritems()
for key, value in dict.iteritems():
    pass
```

```python 3
#In python 3 the method is now just items()
for key, value in dict.items():
    pass
```
Here is an example of how to do this

```python
x = {'stu1':'James', 'stu2':'Bob', 'stu3':'Rengar'}

for stu_id, name in x.items():
    print("{}'s name is {}".format(stu_id, name))
```

### Loops: Iterative vs Recursive

Iteration and recursion each involve a termination test: Iteration terminates when the loop-continuation condition fails; recursion terminates when a base case is recognized.

Recursion repeatedly invokes the mechanism, and consequently the overhead, of method calls. This can be expensive in both processor time and memory space. In almost all cases it is better to use iterative loops.

**Iteration**

When a loop repeatedly executes until the controlling condition becomes false.

**Recursion**

When a statement in a function calls itself repeatedly.  

---
**Continue to Performance Lab:** 3E

---

|[Lab 3E](/03_Flow_Control/lab3e.md)|
|---|
