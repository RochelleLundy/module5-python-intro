# Module 5: Introduction to Python

Python is an extremely powerful open-source _programming language_. It is considered a "high-level", "general purpose" language in that offers strong abstractions on computer instructions (and in fact often reads like badly-punctuated English), and can be used effectively for a wide variety of purposes.
Python is one of the most popular programming languages in the world, and very approachable for beginners and experts alike. Python will be the primary programming language for this course.


<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Contents**

- [Resources](#resources)
- [Programming with Python](#programming-with-python)
  - [Versions](#versions)
- [Running Python Scripts](#running-python-scripts)
  - [Command-Line](#command-line)
  - [Jupyter Notebooks](#jupyter-notebooks)
- [Python Basics](#python-basics)
- [Comments](#comments)
- [Variables](#variables)
  - [Data Types](#data-types)
- [Getting Help](#getting-help)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Resources
Python is an incredibly popular programming language and is especially accessible to new programmers. As such, there are **a lot** of resources available for learning how to program in Python. While these modules will cover most of the details you need, I've included a number of other effective resources below in case you need further help. _Note that you'll need to reference Python 3 materials_.

- [Think Python (Downey)](http://greenteapress.com/wp/think-python-2e/): a free, friendly introductory textbook for learning Python. You should definitely read [**Chapter 1**](http://greenteapress.com/thinkpython2/html/thinkpython2002.html), which is a great overview of programming in general.
- [Python for Everybody (Severance)](http://www.pythonlearn.com/book.php): a remixed version of the above book, with a focus on Information Sciences. See in particular the [interactive version](https://books.trinket.io/pfe/index.html). Chapter 1 of this book is also a very good read.
- [Automate the Boring Stuff with Python (Sweigart)](https://automatetheboringstuff.com/): another good free textbook
- [Python for Non-Programmers Index](https://wiki.python.org/moin/BeginnersGuide/NonProgrammers): an extensive list of resources and materials for learning to program with Python. The textbooks and interactive courses are all good options.
- [Official Python Documentation](https://docs.python.org/3/)
- [Google's Python Style Guide](https://google.github.io/styleguide/pyguide.html)

Specific resources for the material in this module:

- [Python Basics (Sweigart)](https://automatetheboringstuff.com/chapter1/)
- [Variables, expressions, statements (Downey)](http://openbookproject.net/thinkcs/python/english3e/variables_expressions_statements.html)
- [Jupyter Notebook Documentation](http://jupyter-notebook.readthedocs.io/en/latest/notebook.html)
- [Jupyter Notebook Tutorial (Data Camp)](https://www.datacamp.com/community/tutorials/tutorial-jupyter-notebook#gs.MFPIJdI)

## Programming with Python
Python is a **high-level, general-purpose programming language** that can be used to declare complex instructions for computers (e.g., for working with information and data). It is an **open-source** programming language, which means that it is free and continually improved upon by the Python community.

- _Fun Fact:_ Python is named after British comedy troupe "Monty Python", because it seemed like a good idea at the time.

So far in this course you've leveraged formal language to give instructions to your computers, such as by writing syntactically-precise instructions at the command-line. Programming in Python will work in a similar manner: you will write instructions using Python's special language and syntax, which the computer will **interpret** as instructions for how to work with data.

Indeed, Python is an **interpreted language**, in that the computer (specifically the _Python Interpreter_) translates the high-level language into machine language _on the fly at runtime_. The interpreter will read an execute one line of code at a time, executing that line before it even begins to consider the next. This is in contrast with _compiled languages_ (like C or Java) that has the computer do the translation in one pass, and then only execute the program after the whole thing is converted to machine language.

- This means that Python is technically a little slower to execute commands than C or Java because it needs to both translate and execute at once, but not enough that we'll notice.

While it's possible to execute Python instructions one at a time, it's much more common to write down all of the instruction in a single **script** so that the computer can execute them all at once. Python scripts are saved as files with the **`.py`** extension, You can author Python scripts in any text editor (such as VS Code), but we'll also write and run Python code in an interactive web application called Jupyter.

### Versions
Python was first published by Dutch programmer [Guido Van Rossum](https://en.wikipedia.org/wiki/Guido_van_Rossum) in 1991. Although the language is open-source (and so can be [contributed to](https://vimeo.com/1093745) by anyone), Van Rossum still retains a lot of influence over where the language goes, and is known as Python's "Benevolent Dictator for Life".

Version 2.0 of Python was released in 2000, and version 3.0 was released in 2008. However, unlike with many other programming languages that release new versions, Python 2 and Python 3 are **not** compatible with one another: Python 2 code usually won't execute with Python 3 interpreter, and Python 3 code usually won't execute with a Python 2 interpreter.

Python 3 involved a major restructuring which included a number of "breaking" changes to core parts of the language. The most noticeable of these are that all text strings support [Unicode](https://en.wikipedia.org/wiki/Unicode) (non-English characters), `print` is a function not a statement, and integers don't use floor devision (these concepts are discussed in more detail below).

In short, Python 3 is considered the "current" version, and Python 2 is considered the "legacy" version. However Python 2 is still considered "supported" (in terms of bug fixes, etc), and some external libraries have not yet been updated to Python 3. Thus in practice there are two incompatible versions of Python that are used in the world. See [Python2orPython3](https://wiki.python.org/moin/Python2orPython3) for more details.

- In this course, we will be using **Python 3**, particularly as it fixes some issues that often trip up beginners, and is supported by all major libraries in a more effective way.


## Running Python Scripts
Python scripts (programs) are just a sequence of instructions, and there are a couple of different ways in which we can tell the computer to execute these instructions.

### Command-Line
It is possible to issue Python instructions (run lines of code; called **statements**) one-by-one at the command-line by starting an **interactive Python session** within your terminal. This will allow you to type Python code directly into the terminal, and your computer will interpret and execute each line of code (if you just typed Python syntax directly into the terminal, your computer wouldn't understand it).

With Python installed, you can start an interactive Python session on a by running the **`python`** program (simply type the `python` command if you've installed it on the `PATH` via Anaconda).

- On Windows using the Git Bash shell, you may need to utilize [winpty](https://github.com/rprichard/winpty) to connect the Bash shell to the Python output: see [here](http://stackoverflow.com/questions/32597209/python-not-working-in-the-command-line-of-git-bash) for an example). On my machine, using `winpty python` works well.

- Note that if you haven't installed Python via Anaconda, or have multiple versions installed, you may need to use the `python3` command to run a Python 3 session.

This command will start the session, providing some information about the version of Python being run:

![Interactive Python session](img/python-interactive-session.png)

Once you've started running an interactive Python session, you can begin entering one line of code at a time at the prompt (`>>>`). This is a nice way to experiment with the Python language or to quickly run and test some code.

- You can exit this session by typing the `quit()` command, or hitting `ctrl-z` (followed by Enter on Windows).

It is more common though to run entire scripts (`.py` files) from the command-line by using the `python` command and specifying the script file you wish to execute:

![Run Python script from terminal](img/python-terminal.png)

This will cause each line in the script to be run one at a time. This is the "normal" way of running Python programs: you write Python scripts using an editor such as VS Code, and then execute those scripts on the command-line to see them in action.

### Jupyter Notebooks
Another popular and effective way of writing and running Python code is to utilize a [Jupyter Notebook](http://jupyter.org/). A Jupyter Notebook is a **web appplications** (that runs in your web browser) and provides an interactive platform for running Python code: you are able to write and execute Python code write in the browser, similar to an interactive session (but with the ability to write multiple lines of code).

- Jupter is a portmanteau of "Julia", "Python" and "R", which are the programming languages the application was designed to support. Each notebook runs on an individual **kernel** or language interpreter; you'll want to be sure you're running a Python 3 kernel for this course.

Code is authored in individual "notebooks", which are collections of _cells_ (blocks of code or text). Cells can also include Markdown content, allowing notebooks to act as interactive documents with embedded, runnable code.

The Jupyter program is part of the Anaconda package, and so should be installed along with Python. You can start Jupyter from the command-line with:

```bash
jupyter notebook
```

This will open up your web browser with an interface to create or open a notebook relative to the folder you started Jupyter from:

![Opening notebook animation, from the official documentation](http://jupyter-notebook.readthedocs.io/en/latest/_images/new-notebook.gif)

You can also open a particular notebook (which are saved as files with the `.ipynb` extension) by passing the notebook name as an argument:

```bash
jupyter notebook my-notebook.ipynb
```

- To stop running the Jupyter notebook server, hit `ctrl-c` in the terminal and follow the prompts.

Jupyter notebooks are made up of a series of _cells_, each representing a set of code or text. Cells by default are used for Python code, but can also be set to use Markdown by selecting from the dropdown menu.

You can type code directly into the cells, just as if you were typing into a text editor. In order to execute the code in a cell, press **`shift-enter`** or select `Cell > Run Cell` from the menu. Any output from the cell will appear immediately below it. You can add new cells by hitting the "plus" button on the toolbar.

- **Pro-tip:** There are lots of keyboard shortcuts available for working with cells. Click the keyboard icon on the toolbar to see a list of shortcuts.


## Python Basics
<!-- For this module's details about basic Python syntax and variables, see the [accompanying Jupyter notebook](module.ipynb). The contents of the notebook can be read on Github, but you can also **`clone`** this module to your local machine (see [module 4](../../../module4-git-basics) in order to run the example code blocks yourself.
- Practicing with examples and experimenting with different objects is an ideal way to learn programming concepts! -->

## Comments
Before discussing how to program with Python, we need to talk about a piece of syntax that lets you comment your code. In programming, **comments** are bits of text that are _not interpreted as computer instructions_&mdash;they aren't code, they're just notes about the code! Since computer code can be opaque and difficult to understand, we use comments to help write down the meaning and _purpose_ of our code. While a computer is able to understand the code, comments are there to help _people_ understand. This is particularly imporant when someone else will be looking at your work&mdash;whether that person is a collaborator, or is simply a future version of you (e.g., when you need to come back and fix something and so need to remember what you were even thinking). Comments should be clear, concise, and helpful&mdash;they should provide information that is not "obvious" from the code itself.

In Python, we mark text as a comment by putting it after the pound/hashtag symbol (**`#`**). Everything from the `#` until the end of the line is a comment. We put descriptive comments _immediately above_ the code it describes, but you can also put very short notes at the end of the line of code (preferably following two spaces):

```python
# Set how many bottles of beer are on the wall
bottles = 99 - 1  # 98
```

(You may recognize this `#` syntax and commenting behavior from the command-line and git modules. That's because the same syntax is used in a Bash shell!)


## Variables
Since computer programs involve working with lots of _information_, we need a way to store and refer to this information. We do this with **variables**. Variables are labels for information; in Python, you can think of them as "nametags" for data. After giving data a variable nametag, you can then refer to that data by its name.

Variable names can contain any combination of letters, numbers, or underscores (`_`). Variables names must begin with a letter. Note that like everything in programming, variable names are case sensitive. It is best practice to make variable names descriptive and information about what data they contain. `a` is not a good variable name. `cups_of_coffee` is a good variable name. To comply with [Google's Style Guidelines](https://google.github.io/styleguide/pyguide.html#Naming) variables should be **all lower-case letters, separated by underscores (`_`)**.

We call putting information in a variable **assigning** that value to the variable. We do this using the _assignment operator_ **`=`**. For example:

```python
# Stores the number 7 into a variable called shoe.size
shoe_size = 7
```

- _Notice:_ the variable name goes on the left, the value goes on the right!

You can see what value (data) is inside a variable by either typing that variable name as a line of code, or by using R's built-in `print()` function (more on functions later):

```python
print(shoe_size)
## 7
```

You can also use **mathematical operators** (e.g., `+`, `-`, `/`, `*`) when assigning values to variables. For example, you could create a variable that is the sum of two numbers as follows:

```python
x = 3 + 4
```

- A combination of variables, values, operators, or functions that the interpreter needs to _evaluate_ is called an **expression**.

Once a value (like a number) is assigned a variable&mdash;it is _in_ a variable&mdash;you can use that variable in place of any other value. So all of the following are valid:

```python
x = 2  # store 2 in x
y = 9  # store 9 in y
z = x + y  # store sum of x and y in z
print(z)  # 11
z = z + 1  # take z, add 1, and store result back in z
print(z)  # 12
```

**Important** despite using an equal sign (`=`), variable assignments _do not_ specify equalities! Assigning one variable to another does not cause them to be "linked"; changing one variable will leave the other unchanged:

```python
x = 3
y = 4
x = y  # assign the value of y (4) to x
print(x)  # 4
y = 5
print(x)  # 4;
```

Changing the value named `y` does not change the value named `y`, even if the value from `y` was put into the `x` variable at some point.

- _Tip_: when reading or writing code, try to think “x is assigned 3” or “x gets the value 3”, rather than "x equals 3".


### Data Types
In the example above, we stored **numeric** values in variables. Python is a **dynamically typed language**, which means that we _do not_ need to explicitly state what type of information will be stored in each variable we create. The Python interpreter is intelligent enough to understand that if we have code `x = 7`, then `x` will contain a numeric value (and so we can do math upon it!)

You can "look up" the type of a particular value by using the `type()` function:

```python
type(7)  # integer
## <class 'int'>

type("Hello")  # string
## <class 'str'>
```

- Type is also referred to as `class` (i.e., "classification"). **Classes** are ways of structuring information and behavior in computer programs; we will discuss them in more detail later.

There are a number of "basic types" for data in Python. The two most common are:

- [**Numeric Types**](https://docs.python.org/3/library/stdtypes.html#typesnumeric): Python has two data types used to represent numbers: `int` (integer) for _whole numbers_ like `7` and `float` for decimals like `3.14`.

  We can use **mathematical operators** on numeric data (such as `+`, `-`, `*`, `/`, etc.). There are also numerous functions that work on numeric data (such as for calculating sums or averages). You can mix and match ints and floats in mathematical expressions; the result will be a float if either of the operators are floats. Division (`/`) always produces a float; use the "integer division operator" `//` to force the result to be a whole number (rounded down).

- [**Strings**](https://docs.python.org/3/library/stdtypes.html#text-sequence-type-str): Python uses the `str` (string) type to store textual data. `str` values contain _strings_ of characters, which are the things you type with a keyboard (including digits, spaces, punctuation, and even line breaks). You specify that some characters are a string by surrounding them in either single quotes (**`'`**) or double quotes (**`"`**).

  ```python
  # Create a string variable `famous_poet` with the value "Bill Shakespeare"
  famous_poet = "Bill Shakespeare"
  ```

  Note that string literals (the text in quotes) are _values_ just like numeric literals (numbers), so can be assigned to variables!

  - Using "triple-quotes" will allow you to specify a multi-line string:

    ```python
    message = """Dear Professor,
                 My dog ate my homework.
                 Thank you,
                    A. Student
              """
    ```

  Strings support the `+` operator, which performs **concatenation** (combining two strings together). For example:

  ```python
  # concatenate 3 strings. The middle string is a space character
  full_name = "Bill" + " " + "Shakespeare"
  ```

  The operands must both be strings. Also note that concatenating strings doesn't add any additional characters such as spaces between words; you need to handle such punctuation yourself!

  There are many built-in functions for working with strings, and in fact strings support a [variety of functions](https://docs.python.org/3/library/stdtypes.html#string-methods) you can call _on_ them. See [module 6](../../../module6-functions) for details.

Note that there are many other data types as well; more will be introduced throughout the remaining modules.

It is possible to convert from one type to another by using a **type converter function**, which is usually named after the type you wish to convert _to_:

```python
int(3.14)   # 3
int(5.98)   # 5 (takes the floor value)
float(6)    # 6.0
str(2)      # "2"
int("2")    # 2
int("two")  # ValueError!
```

This is particularly useful when you wish to include a number in a string:

```python
favorite_number = 12
message = "My favorite number is "+str(favorite_number)
print(message)  # My favorite number is 12
```

For practice creating and working with variables (as well as with Jupyter noteookes), see [exercise-1](exercise-1).

## Getting Help
As with any programming language, when working in Python you will inevitably run into problems, confusing situations, or just general questions. Here are a few ways to start getting help.

1. **Read the error messages**: If there is an issue with the way you have written or executed your code, Python will often print out an error message. Do you best to decipher the message (read it carefully, and think about what is meant by each word in the message), or you can put it directly into Google to get more information. You'll soon get the hang of interpreting these messages (and how to resolve common ones) if you don't panic when one appears. _Remember: making mistakes is normal!_

2. **Google**: When you're trying to figure out how to do something, it should be no surprise that Google is often the best resource. Try searching for queries like `"how to <DO THING> in Python"`. More frequently than not, your question will lead you to a Q/A forum called StackOverflow (see below), which is a great place to find potential answers.

3. **StackOverflow**: StackOverflow is an amazing Q/A forum for asking/answering programming questions. Most basic questions have already been asked/answered here. However, don't hesitate to post your own questions to StackOverflow. Be sure to hone in on the specific question you're trying to answer, and provide error messages and sample code as appropriate. I often find that, by the time I can articulate the question enough to post it, I've figured out my problem anyway.

    - There is a classical method of debugging called [rubber duck debugging](https://en.wikipedia.org/wiki/Rubber_duck_debugging), which involves simply trying to explain your code/problem to an inanimate object (talking to pets works too). You'll usually be able to fix the problem if you just step back and think about how you would explain it to someone else!

4. **Documentation**: Python's [documentation](https://docs.python.org/3/) is pretty good: very thorough and usually contains helpful examples. The only problem is that it can be too detailed for our purposes, and can sometimes be hard to navigate (where to find information is not immediately obvious in some situations). Searching the documentation is a good way to narrow down what you're looking for.
