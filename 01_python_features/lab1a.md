|[Return to Table of Contents](/00-Table-of-Contents.md)|
|---|

---

# Lab 1A

Now that we learned the background behind Python, lets get to coding. Since Python is cross-platform, you can use whatever OS and text editor/IDE that you'd like. Below are my recommendations:

### Recommended editors:

* Vim \(terminal based: steep learning curve\)
* Nano \(terminal based\)
* Visual Studio Code
* Sublime
* Atom
* Brackets
* Notepad++

### Recommend against:

* Visual Studio
* Eclipse
* PyCharm
* EMacs
* etc

We flat out do not need a full fledged IDE for training. Python is easy to understand and type. We are going to focus on being independent and debugging with our own debugging code.

## If your Python is out of date \(2.7.15 & 3.7\):

### Python2

**Fedora:**

```text
sudo dnf install python2
```

* The command for python2 in Fedora will be: _python_ or _python2_

**Windows:**

* Install latest from [https://www.python.org/downloads/windows/](https://www.python.org/downloads/windows/)
* Ensure you check the PATH setup box during install
* The command for python2 in Windows will be: _py -2_

### Python3

**Fedora:**

```text
sudo dnf install python37
```

* The command for python37 in Fedora will be: _python3.7_
  * Though that's a bit of a pain to write... so feel free to create an alias
  * I myself will be using tese aliases:

    ```text
    alias py37=python3.7
    alias python37=python3.7
    ```

**Windows:**

* Install latest from [https://www.python.org/downloads/windows/](https://www.python.org/downloads/windows/)
* Ensure you check the PATH setup box during install
* The command for python3 in Windows will be: _py_

---

|[Next Topic](/01_python_features/04_py2_py3.md)|
|---|
