|[Table of Contents](/00-Table-of-Contents.md)|
|---|

---

## Break and Continue

If further examples are needed of how Break/Continue works, please reference PyDocs.

### Break

The break statement simply breaks out of the innermost enclosing loop.

```python
for i in range(1, 101):
    if i == 10:
        print("WE BROKE IT!")
        break
    print(i)
```

**Output:**

```text
1
2
3
4
5
6
7
8
9
WE BROKE IT!
```

### Continue

The continue statement continues with the next iteration of the loop.

```python
for i in range(1, 100):​
    if i % 2 == 0:​
        print("{} is an even number!".format(i)​)
        continue #prevents second print from running​
    print("{} is an odd number!".format(i))
```

**Output:**

```text
1 is an odd number!
2 is an even number!
3 is an odd number!
4 is an even number!
5 is an odd number!
6 is an even number!
7 is an odd number!
8 is an even number!
9 is an odd number!
10 is an even number!
11 is an odd number!
12 is an even number!
13 is an odd number!
14 is an even number!
15 is an odd number!
16 is an even number!
17 is an odd number!
18 is an even number!
19 is an odd number!
20 is an even number!
....
```

Notice how the second print is skipped entirely for even numbers!  

---

**Continue to Performance Lab:** 3F

---

|[Lab 3F](/03_Flow_Control/lab3f.md)|
|---|
