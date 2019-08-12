|[Return to Table of Contents](/00-Table-of-Contents.md)|
|---|

## While Loops

While loops, just like C and C++, loop through each iteration until either the condition is met or a break statement is called. Being that this is a loop... it is possible and rather easy to get stuck in an infinite loop. Keep in mind, you cannot use the x++ incrementer in Python.

```python
count = 0
while count < 10:
    print('count: ' + str(count))
    count += 1
```

**Output:**

```text
count: 0
count: 1
count: 2
count: 3
count: 4
count: 5
count: 6
count: 7
count: 8
count: 9
```

When using the while loop, a few factors will make a difference in the output... that could break your program if you don't pay attention. The value of the incrementing var, where the count increment is placed and the comparison operator are the three most common factors. Here are a few things to keep in mind:

* It's common practice to increment your var after the bulk of the code is executed \(count += 1\)
* With that said, setting the count equal to 0 will start the output at 0, 1 will start at 1... etc
* It's best practice to change the comparison operator rather than the 'increment to number'. For instance, count is currently set to increment until 10. Since the code increments after the print is executed... the last count printed is 9, even though the count really ends on 10. If you follow the above factors, changing the comparison operator to **&lt;=** will result in an output that prints count: 10 without effecting code that relies on count. 

## While Else

Python allows for the use of a **While-Else Statement.** The while-else runs like a regular while loop except for the one iteration when the while loop becomes false. This results in the else statement being executed once!

```python
count = 0
while count <= 10:
    print('count: {}'.format(count))
    count += 1
else:
    print('while loop executed... count is: {}'.format(count))
```

**Output:**

```text
count: 0
count: 1
count: 2
count: 3
count: 4
count: 5
count: 6
count: 7
count: 8
count: 9
count: 10
while loop executed... count is: 11
```

This gives us a clearer look at how Python increments variables.  

---

**Continue to Performance Lab:** 3D  

---

|[Lab 3D](/03_Flow_Control/lab3d.md)|
|---|
