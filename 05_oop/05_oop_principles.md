|[Table of Contents](/00-Table-of-Contents.md)|
|---|

---

## OOP Principles

**Object Oriented:**  Programming typified by a data-centered \(as opposed to a function-centered\) approach to program design.

## [The Zen of Python](https://www.python.org/doc/humor/#id1)

> Beautiful is better than ugly.  
> Explicit is better than implicit.  
> Simple is better than complex.  
> Complex is better than complicated.  
> Flat is better than nested.  
> Sparse is better than dense.  
> Readability counts.  
> Special cases aren't special enough to break the rules.  
> Although practicality beats purity.  
> Errors should never pass silently.  
> Unless explicitly silenced.  
> In the face of ambiguity, refuse the temptation to guess.  
> There should be one-- and preferably only one --obvious way to do it.  
> Although that way may not be obvious at first unless you're Dutch.  
> Now is better than never.  
> Although never is often better than  
> _right_  
>  now.  
> If the implementation is hard to explain, it's a bad idea.  
> If the implementation is easy to explain, it may be a good idea.  
> Namespaces are one honking great idea -- let's do more of those!  
> —Tim Peters

Capturing the essential internal state and methods that cause state change is the first step in good class design. We can summarize some helpful design principles using the acronym **S.O.L.I.D**.:

* **Single Responsibility Principle**

  A class should have one clearly defined responsibility.

* **Open/Closed Principle**

  A class should be open to extension-generally via inheritance, but closed to modification. We should design our classes so that we don't need to tweak the code to add or change features.

* **Liskov Substitution Principle**

  We need to design inheritance so that a subclass can be used in place of the superclass.

* **Interface Segregation Principle**

  When writing a problem statement, we want to be sure that collaborating classes have as few dependencies as possible. In many cases, this principle will lead us to decompose large problems into many small class definitions.

* **Dependency Inversion Principle**

  It's less than ideal for a class to depend directly on other classes. It's better if a class depends on an abstraction, and a concrete implementation class is substituted for the abstract class.

The goal is to create classes that have the proper behavior and also adhere to the design principles.

### Function Style {#ch45lev1sec2}

All the other rules I’ve taught you about how to make a function nice apply here, but add these things:

• For various reasons, programmers call functions that are part of classes `methods`. It’s mostly marketing but just be warned that every time you say “function” they’ll annoyingly correct you and say “method.” If they get too annoying, just ask them to demonstrate the mathematical basis that determines how a “method” is different from a “function,” and they’ll shut up.

• When you work with classes, much of your time is spent talking about making the class “do things.” Instead of naming your functions after what the function does, instead name it as if it’s a command you are giving to the class. For example, `pop` essentially says, “Hey list, pop this off.” It isn’t called `remove_from_end_of_list` because, even though that’s what it does, that’s not a _command_ to a list.

• Keep your functions small and simple. For some reason, when people start learning about classes, they forget this.

### Class Style {#ch45lev1sec3}

• Your class should use “camel case” like `SuperGoldFactory` rather than `super_gold_factory`.

• Try not to do too much in your `__init__` functions. It makes them harder to use.

• Your other functions should use “underscore format” so write `my_awesome_hair` and not `myawesomehair` or `MyAwesomeHair`.

• Be consistent in how you organize your function arguments. If your class has to deal with users, dogs, and cats, keep that order throughout unless it really doesn’t make sense. If you have one function that takes `(dog, cat, user)` and the other takes `(user, cat, dog)`, it’ll be hard to use.

• Try not to use variables that come from the module or globals. They should be fairly self-contained.

• A foolish consistency is the hobgoblin of little minds. Consistency is good, but foolishly following some idiotic mantra because everyone else does is bad style. Think for yourself.

• Always, _always_ have `class Name(object)` format or else you will be in big trouble.

### Code Style {#ch45lev1sec4}

• Give your code vertical space so people can read it. You will find some very bad programmers who are able to write reasonable code but who do not add _any_ spaces. This is bad style in any language because the human eye and brain use space and vertical alignment to scan and separate visual elements. Not having space is the same as giving your code an awesome camouflage paint job.

• If you can’t read it out loud, it’s probably hard to read. If you are having a problem making something easy to use, try reading it out loud. Not only does this force you to slow down and really read it, but it also helps you find difficult passages and things to change for readability.

• Try to do what other people are doing in Python until you find your own style.

• Once you find your own style, do not be a jerk about it. Working with other people’s code is part of being a programmer, and other people have really bad taste. Trust me, you will probably have really bad taste too and not even realize it.

• If you find someone who writes code in a style you like, try writing something that mimics that style.

### Good Comments {#ch45lev1sec5}

• There are programmers who will tell you that your code should be readable enough that you do not need comments. They’ll then tell you in their most official sounding voice, “Ergo one should never write comments. QED.” Those programmers are either consultants who get paid more if other people can’t use their code or incompetents who tend to never work with other people. Ignore them and write comments.

• When you write comments, describe _why_ you are doing what you are doing. The code already says how, but why you did things the way you did is more important.

• When you write doc comments for your functions, make the comments documentation for someone who will have to use your code. You do not have to go crazy, but a nice little sentence about what someone can do with that function helps a lot.

• Finally, while comments are good, too many are bad, and you have to maintain them. Keep your comments relatively short and to the point, and if you change a function, review the comment to make sure it’s still correct.

#### Reference: [PEP8 Style Guide](https://www.python.org/dev/peps/pep-0008/)

---

|[Next Topic](/05_oop/06_oop_terminology.md)|
|---|
