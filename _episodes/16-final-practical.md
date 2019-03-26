---
title: "Final practical: How Many Articles Reference that they use R and/or Python?"
teaching: 30
exercises: 60
questions:
- "Can I write a command line Python progam using ArgParse?"
objectives:
- "Write a Python script that accepts arguments."
- "Write a Python script opens a file and searches for words."
- "Document your Python script using comments."
keypoints:
- "XXXXXXX"
- "XXXXXXX"
- "XXXXXXX"
- "XXXXXXX"
---

## Final Practical

* This final practicle is going to combine all that you have learnt about Python into one command line program!
* The challenge is to write a command line Python progam using Argparse (under version control) that can:
	* Open a plain text file of a research article.
	* Search the article for references to `R` and/or `Python`.
		* <i>bonus: search for the versions of `R` or `Python`.<i/>
	* Return the number of times the article refers to `R` and/or `Python`.
	* Choose whether or not to save the output and choose the output file name.

## Example articles
### Python PDF and XML
* https://journals.plos.org/ploscompbiol/article/file?id=10.1371/journal.pcbi.1005871&type=printable
* https://journals.plos.org/ploscompbiol/article/file?id=10.1371/journal.pcbi.1005871&type=manuscript

### Python and R PDF and XML
* https://journals.plos.org/ploscompbiol/article/file?id=10.1371/journal.pcbi.1005510&type=printable
* https://journals.plos.org/ploscompbiol/article/file?id=10.1371/journal.pcbi.1005510&type=manuscript

### R PDF and XML
* https://journals.plos.org/ploscompbiol/article/file?id=10.1371/journal.pcbi.1004140&type=printable
* https://journals.plos.org/ploscompbiol/article/file?id=10.1371/journal.pcbi.1004140&type=manuscript

### Need an Example of a Paper for without reference to either

## Part 1 - Setup of Git Repository and Python Script

Open `Git Bash` and move to the directory where you want to work with your new Python project <br/>
Now we need to initiate our new `Git Repository` so that we have our work under version control!

~~~
git init python_prac
~~~
{: .language-bash}

Next lets create our Python program by opening your chosen text editor and save it with an appropriate name. <br/>
e.g. using VIM in `Git Bash`.

~~~
Vim ref_finder.py
~~~
{: .language-bash}

Run `git status` to see if our new file is under version control.

~~~
git status
~~~
{: .language-bash}
~~~

~~~
{: .output}
