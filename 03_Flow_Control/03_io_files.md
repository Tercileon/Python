|[Table of Contents](/00-Table-of-Contents.md)|
|---|

---

## I/O: Files

#### Reference: [File Objects](https://docs.python.org/2.7/library/stdtypes.html#bltin-file-objects)

Python offers a robust and insanely easy to use toolset to interact with files.

First, a file must be opened before it can be modified... this includes creating new files. We use the **open\(\)** function to achieve this. The first argument passed is the file name; rather it exists or not. The second argument is the operation in which we would like to perform. ex read, write, overwrite, etc.

```python
file = open("file.txt", 'r')
```

## open\(\) Operation Arguments

### read

**r** -- Opens file for read only. File pointer is placed at start of file.

**rb** -- Opens a file for reading only in binary format. The file pointer is placed at the start of the file.

**r+** -- Opens a file for both reading and writing. File pointer is placed at the start of the file.

**rb+** -- Opens a file for both reading and writing in binary format. File pointer is placed at the start of the file.

### write

**w** -- Opens a file for writing only. Overwrites the file if it exists. If the file does not exist, it creates a new one.

**wb** -- Opens a file for writing only in binary format. Overwrites the file if it exists. If it does not exist, it creates a new one.

**w+** -- Opens a file for writing and reading. Overwrites the existing file if it exists. If it does not exist, it creates a new one.

**wb+** -- Opens a file for writing and reading in binary format. Overwrites the existing file if it exists. If not, it creates a new one.

### append

**a** -- Opens a file for appending. File pointer is at end of file if it exists. If the file does not exist, it creates a new one

**ab** -- Opens a file for appending in binary format. File pointer is at end of file if it exists. If not, it creates a new one.

**a+** -- Opens a file for both appending and reading. If file exists, file pointer placed at end of file. If not, it creates a new one.

**ab+** -- Opens a file for both appending and reading in binary format. Follows above file pointer and write rules.

## Advantages of Using Binary Formatting

The advantages of using binary formatting primarily apply to Windows. Unlike Linux, where "everything is a file"... Windows treats binaries and files differently. Thus, reading binary in text mode in Windows will more than likely result in corrupted data. Passing a 'b' variant will mitigate this issue.

## File Operations

Once the file is open, we can begin reading, adding or modifying the file's contents. Below are some of the methods to make that happen.

* **f.write\(str\)**
  * write str to file​
* **f.writelines\(str\)**
  * write str to file​
* **f.read\(sz\)**
  * read size amount​
* **f.readline\(\)**
  * read next line​
* **f.seek\(offset\)**
  * move file pointer to offset​
* **f.tell\(\)**
  * current file position​
* **f.truncate\(sz\)**
  * truncate the files z bytes​
* **f.mode\(\)**
  * returns the access mode used to open a file
* **f.name\(\)**
  * returns the name of a file
* **f.close\(\)**
  * close file handle​... 
  * Just like other programming languages, we need to close the stream
  * **ALWAYS CLOSE THE FILE AS SOON AS YOU'RE FINISHED USING IT!!**

```python
f = open('file_name', 'a')
data = f.read()
print data

file.close()
```  

---

**Continue to Performance Lab:** 3B  

---

|[Lab 3B](/03_Flow_Control/lab3b.md)|
|---|
