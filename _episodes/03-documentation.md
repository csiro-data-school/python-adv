---
title: "Getting Help When You Need It: Working with Documentation"
teaching: 10
exercises: 15
questions:
- "Where is the Python documentation and how do I use it?"
- "How can the `help()` function be used?"
- "What does the `type()` function do?"
objectives:
- "Understand how to find and navigate the online Python documentation."
- "Understand how to select the documentation for your specific Python version."
- "Be able to use `help()` to get help on specific Python objects."
- "Understand the relative merits of `help()` vs the online documentation."
- "Know how to use the `type()` function to query the type of a Python object."
keypoints:
- "[The official Python documentation](python-documentation) is a good reference
  to the core Python language."
- "You should ensure that the correct Python version is selected in the online
  documentation, as language features have changed over time."
- "There are several ways to check the Python version you are using."
- "The `help()` function displays the documentation for a given Python object."
- "In Jupyter Notebooks, the `?` command will display the same result as
  `help()` in a separate panel, with formatted text."
- "The `type()` function returns the type of a Python object."

---

## The Python Documentation

The official documentation is a good place to start for any language. [The
official Python documentation][python-documentation] is generally well
organised and described, so this episode only highlights a few aspects.

The first thing to note is that the url
[https://docs.python.org/](https://docs.python.org/) automatically redirects you
to the most recent stable release of Python. If you require documentation for
a specific version, it can be selected by the drop-down box at the top left of
the page. Selecting the right language version is important, as many language
features have changed over time.

There are several ways to check the version of Python you are using, including:

- From a command-line, the commands `python --version` and `python3 --version`
  will report the full version.
  - Note that `python --version` may report that it is either Python 2 or 3. On
    systems where `python` is Python 2, it is common for `python3` to also be
    present.
- When running an interactive Python interpreter, the version is printed when
  the interpreter starts.
- The version can be checked programmatically:
  ~~~
  import platform
  print(platform.python_version())
  ~~~
  {: .language-python}

> ## Check your version of Python
> Using one of the methods listed above, check the version of Python you are
> using for this course.
>
> Switch to the online documentation for your version.
{: .challenge}

> ## Find and use the `platform` online documentation
> We used the `platform.python_version()` function to retrieve the version
> string for the current Python interpreter. But the `platform` module can tell
> us a lot more information about the version of Python in use, as well as the
> underlying operating system.
>
> Find the documentation for the `platform` module in the online documentation.
> Which function can be used to identify the type of operating system that is
> running Python?
> > ## Solution
> > The platform documentation is in the [Library Reference
> > section][python-library]. It can be found by browsing, using the search bar
> > at the top-right of the page, or by using your browser's search in a page
> > function.
> >
> > The operating system type is returned (if it can be determined) by the
> > `platform.system()` function:
> > [https://docs.python.org/3/library/platform.html#platform.system][platform-system]
> {: .solution}
{: .challenge}

## Get help inside Python: the `help()` function

Knowing how to find and navigate the online documentation is vital, but there
are times when looking something up inside an interactive Python session is also
useful. The built-in `help()` function looks up the documentation for Python
objects. For example:
~~~
>>> help(print)
Help on built-in function print in module builtins:

print(...)
    print(value, ..., sep=' ', end='\n', file=sys.stdout, flush=False)

    Prints the values to a stream, or to sys.stdout by default.
    Optional keyword arguments:
    file:  a file-like object (stream); defaults to the current sys.stdout.
    sep:   string inserted between values, default a space.
    end:   string appended after the last value, default a newline.
    flush: whether to forcibly flush the stream.
~~~
{: .language-python}

> ## Comparing documentation
>
> In Python, the function for opening a file is `open()`. In an interactive
> Python interpreter, use `help()` to display help for `open`.
>
> Now look at [the online documentation][python-open] for `open`. Which provides the most
> help? Is the content the same or different? Which is easier to use? When might
> you use one or the other?
> > ## Solution
> > The code to access help on `open` is:
> > ~~~
> > help(open)
> > ~~~
> > {: .language-python}
> >
> > As to whether `help()` is more or less helpful than the online
> > documentation, there is no right answer. But is good to have options.
> {: .solution}
{: .challenge}

> ## Jupyter Notebook Specific Help
> In a [Jupyter Notebook][jupyter], there is another option for the `help()`
> function.  Instead of calling `help()`, simply prepend a Python object with
> `?` to display HTML formatted help in a separate panel. If you are using or
> have access to a Jupyter Notebook, compare the output from the following two
> statements:
> ~~~
> help(print)
>
> ?print
> ~~~
> {: .source}
{: .callout}

## Checking on Types: the `type()` function

Python is a *duck-typed* language. Sometimes it isn't necessary to ensure that
variables are a specific type, it can be sufficient to simply try to use
variables in the required way. They will either *walk like a duck*, and the
operation will work, or an exception will be raised (see the [exceptions
episode]({{ page.root }}/05-exceptions/)).

However, sometimes it is helpful to check on the exact type of a variable. This
can be done with the built-in `type` function. `type` will accept any Python
object, including variables and literal values.

> ## Exploring the `type()` Function
> In an interactive Python console, or a Jupyter Notebook, execute the following
> code snippets. What does the output mean?
> ~~~
> # 1
> a = 7
> type(a)
>
> # 2
> type(7)
>
> # 3
> type(int)
>
> # 4
> type("seven")
>
> # 5
> def a_function():
>     pass
> type(a_function)
>
> # 6
> type(print)
> type(if)
> ~~~
> {: .language-python}
> > ## Solution
> > 1. `a` is a variable of type `int`
> > 2. `7` is a literal of type `int`
> > 3. `int` represents a class, and has type `type`. If you define your own
> >    classes, they will also return "<class 'type'>". Note that `type(int)`
> >    does not return `int` since the code is asking for the type of the class
> >    `int` itself. `int` is a class that defines the integers, integers will
> >    have type `int`, but `int` itself is a type.
> > 4. '"seven"' is a string literal. Strings in Python have type `str`.
> > 5. This defines a function called `a_function`. The function does nothing,
> >    but that doesn't alter the fact that it is a function.
> > 6. Both `print` and `if` are built in to the language, so why is one line an
> >    error but not the other? The answer is that `print` is a function and so
> >    has a type, while `if` is a language keyword. Keywords are parsed by the
> >    language but do not typically result in a typed runtime object.
> {: .solution}
{: .challenge}


{% include links.md %}

[python-documentation]: https://docs.python.org/3/
[python-library]: https://docs.python.org/3/library/index.html
[platform-system]: https://docs.python.org/3/library/platform.html#platform.system
[python-open]: https://docs.python.org/3/library/functions.html#open
[jupyter]: https://jupyter.org/
