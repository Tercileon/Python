|[Table of Contents](/00-Table-of-Contents.md)|
|---|

---

## Additional Libraries and Modules  

### **A few:**

* sys, os, socket, glob, subprocess, hashlib, shutil, math, json
* struct
* 3rd party
* Paramiko
* pip
* Hitchhikers Guide

### Sys, OS and Subprocess

* **sys module**
  * Contains system level info
  * sys.path, sys.argv, sys.modules
* **os module**
  * interact with the os dependent functionality
  * os.path, os.walk, os.system, os.stat
* **subprocess module**
  * spawn process, stdin/stdout
  * subprocess.Popen\(\)

### Hashlib

Hashlib implements a common interface to many different secure hash and message digest algorithms.

```python
import hashlib

m = hashlib.md5()
m.update("password")
print m.digest()
print m.hexdigest()

x = hashlib.md5()
x.update("password")
print m.digest()

if m.digest() == x.digest():
    print 'access granted'
```

### Struct

Struct performs conversions between Python values and C structs represented as Python strings. This is mostly used in handling binary data in files and network connections. This will be used during Network Programming.

```python
import struct

data = struct.pack('hh1', 1, 2)
print data

data = struct.unpack('hh1', data)
print data
```

### JSON

JSON is a lightweight data interchange format inspired by JavaScript object literal syntax. JSON is used in a whole lot of applications and scenarios.

```python
import json

# JSON to Python
json_string = '{"make": "Ford", "model": "Mustang"}'
parsed_json = json.loads(json_string)
print parsed_json['make']


# Python to JSON
json_d = {
    'make': 'Ford',
    'model': 'Mustang',
    'type': 'Pony',
    'colors': ['red', 'blue', 'white', 'yellow']
}

parsed_d = json.dumps(json_d)
print parsed_d
```

## Paramiko, PIP and the HitchHiker's Guide

### Paramiko

Paramiko is a Python \(2.7, 3.4+\) implementation of SSHv2 protocol. Paramiko utilizes a Python C extension for low level crytography; though Paramiko itself utilizes a Python interface around SSH network concepts.

[http://www.paramiko.org/](http://www.paramiko.org/)

### PIP

pip is a tool for installing Python packages. There is all sorts of packages you can install from virtualenv \(Python virtual environments\), Requests \(http library\) to Scrapy \(webscraping\). Since you have Python already installed, you have pip. Below is an example on how to install virtualenv.

```text
pip install virtualenv
```

Easy. Here is a great list of some of the most popular Python packages.

[https://pythontips.com/2013/07/30/20-python-libraries-you-cant-live-without/](https://pythontips.com/2013/07/30/20-python-libraries-you-cant-live-without/)

### The HitchHiker's Guide

The HitchHiker's guide is an excellent guide on Python that is constantly being updated.

[http://docs.python-guide.org/en/latest/](http://docs.python-guide.org/en/latest/)

---

|[Next Topic](/06_advanced/04_multithreading.md)|
|---|
