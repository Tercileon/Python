|[Table of Contents](/00-Table-of-Contents.md)|
|---|

---

## If, Elif, Else

Just like most other programming languages, Python includes the standard **if**, **else-if**, and **else** statements. The only difference is that Python's else-if statement is shortened to **elif**. The **if** statement checks for truth within a given condition. If the condition is false, the code within the if statement will not run. To counter this, you can use **elif** statements to check for further conditions. Finally we have the **else** statement which is a catch all if none of the previous statements evaluate to True.

Note: If even one statement in an if/elif is evaluated as true, all the remaining conditions will not be checked. Conditions are checked from top to bottom. Some situations call for multiple if statements, some work better with if/elif/else statements. Just keep in mind the order of the statements.

As mentioned in previous lectures, Python does not use brackets. So unlike C, Java, etc... Python uses indentation. To make this work for statements, loops, functions, etc... **Python uses a colon ':' to declare the start of an indented block.**

```python
a = 100
if a > 100:
    print('a is greater than 100')
elif a < 100:
    print('a is less than 100')
else:
print('a is equal to 100')
```

**Output:**

```text
a is equal to 100
```

**Another Example:**

What is the output?

```python
 
for a in range(51):
    if a == 0:
        print("{} you can't divide by zero!".format(a))
    elif a % 10 == 0:
        print ('{} can be divided by 10!!!'.format(a))
    elif a % 2 == 0:
        print('{} is even!'.format(a))
    else:
        print('{} is odd!'.format(a))
```  

---
**Continue to Performance Lab** 3C

---

|[Lab 3C](/03_Flow_Control/lab3c.md)|
|---|
