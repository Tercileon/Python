|[Table of Contents](/00-Table-of-Contents.md)|
|---|

---

## Regular Expressions

Regular expressions, often referred to as REs or regexes, are bits of small and highly specialized programming language embedded inside Python. The PyDocs actually contains an entire page on how to use regex. We will be touching on some of it's functionality... it'll be up to you to utilize the PyDocs and take your knowledge to the next level.

**PyDocs HOWTO**

[https://docs.python.org/3/howto/regex.html](https://docs.python.org/3/howto/regex.html)

**PyDocs Re**

[https://docs.python.org/2/library/re.html](https://docs.python.org/2/library/re.html)

## Using Regular Expressions

**re.compile:** compiles regular expression into pattern objects which allows for repeated use

**re.match:** apply pattern to the start of a string, return match or None

**re.search:** scan through a string, return match or None

**re.findall:** find all matches and return them as a list

**Python re search and compile example:**

```python
import re

search_str = "This is a string to search"
re_search = re.compile("string")
matched_obj = re_search.search(search_str)

print matched_obj
```

```text
<_sre.SRE_Match object at 0x02CBFA68>
```

**Practical Example**

```python
import re

patterns = ['Enterprise', 'Death Star']
pharse = "The Enterprise is the flagship of the Federation."

for pattern in patterns:
    print 'Looking for "{}" in "{}": '.format(pattern, pharse)

    if re.search(pattern, pharse):
        print "found a match!"
    else:
        print "no match!"
```

```text
Looking for "Enterprise" in "The Enterprise is the flagship of the Federation.":
found a match!
Looking for "Death Star" in "The Enterprise is the flagship of the Federation.":
no match!
```

**Python re search start\(\) and end\(\):**

```python
import re

pattern = "Dave"
text = "I'm sorry Dave, I'm afarid I can't do that."

match = re.search(pattern, text)

start = match.start()
end = match.end()

print 'Found "{}" in "{}" from {} to {} ("{}")'.format(match.re.pattern, match.string, start, end, text[start:end])
```

```text
Found "Dave" in "I'm sorry Dave, I'm afarid I can't do that." from 10 to 14 ("Dave")
```

**Python re match example:**

Python's re.match is similar to re.search. The main difference being that match searches only at the start of the string whereas search will apply the pattern to the entire string.

```python
import re

text = "I turned myself into a pickle. I'm Pickle Riiiiick."
text2 = "I did not turn myself into a pickle.  I am not Pickle Riiiiick."

match = re.match("I turned myself", text)
match2 = re.match("I did not", text2)

if match == None:
    print 'Could not find "{}" in "{}"'.format(match.re.pattern, match.string)
else:
    print 'Found "{}" in "{}"'.format(match.re.pattern, match.string)

if match2 == None:
    print 'Cound not find "{}" in "{}"'.format(match2.re.pattern, match2.string)
else:
    print 'Found "{}" in "{}"'.format(match2.re.pattern, match2.string)
```

```text
Found "I turned myself" in "I turned myself into a pickle. I'm Pickle Riiiiick"
Found "I did not" in "I did not turn myself into a pickle.  I am not Pickle Riiiiick."
```

---

|[Next Topic](/06_advanced/03_additional_libaries_modules.md)|
|---|
