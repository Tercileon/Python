|[Table of Contents](/00-Table-of-Contents.md)|
|---|

---

## Multithreading  

![](/assets/Creepy_Kid.jpg)

**Multithreading is similar to running multiple programs concurrently... but better.** 

* Threads within a process share the same data space with the main thread.
* Requires less memory overhead and is cheaper than running multiple processes

**A thread has a beginning, execution sequence and conclusion. An instruction pointer keeps track of where it is currently running.** 

* Threads can be put to sleep, even while other threads are running. 
* Threads can also be pre-empted \(interrupted\)

**Multithreading Example:**

```python
import time
from threading import Thread 

# Work to be done
def sleeper(i):
    print "thread {:d} sleeps for 5 seconds\n".format(i)
    time.sleep(5)
    print "thread {:d} woke up\n".format(i)

# Creating the workers, and passing individual arguments to each of them
for i in range(10):
    t = Thread(target=sleeper, args=(i,))
    t.start()
```

```text
thread 0 sleeps for 5 seconds

thread 1 sleeps for 5 seconds
thread 2 sleeps for 5 seconds
thread 3 sleeps for 5 seconds

thread 4 sleeps for 5 seconds


thread 5 sleeps for 5 seconds


thread 6 sleeps for 5 seconds

thread 7 sleeps for 5 seconds
thread 8 sleeps for 5 seconds


thread 9 sleeps for 5 seconds

thread 9 woke up
thread 7 woke up
thread 6 woke up
thread 4 woke up
thread 2 woke up
thread 1 woke up
thread 8 woke up
thread 0 woke up
thread 5 woke up
thread 3 woke up
```

Your output may not look like mine... that is okay. The time in which the workers start is almost always random due to how concurrent their launch sequences are.

---

|[Next Topic](/06_advanced/05_unit_testing.md)|
|---|
