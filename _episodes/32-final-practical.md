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

>## Part 1 - Setup of Git Repository and Python Program
>
>Open `Git Bash` and move to the directory where you want to work with your new Python project. <br/>
>Now we need to initiate our new `Git Repository` so that we have our work under version control!
>
>>## CHALLENGE: Initiate your git repository
>>>## Solution
>>>~~~
>>>git init python_prac
>>>~~~
>>>{: .language-bash}
>>{: .solution}
>
>Next move to your new git folder `python_prac` and create our Python program by opening your chosen text <br/> 
>editor and saving it with an appropriate name. <br/>
>e.g. using VIM in `Git Bash`. Write a comment `#` at the top of your program stating what it does and then save it.
>
>~~~
>vim ref_finder.py
>~~~
>{: .language-bash}
>
>Run `git status` to see if our new file is under version control.
>
>~~~
>git status
>~~~
>{: .language-bash}
>~~~
>On branch master
>
>No commits yet
>
>Untracked files:
>  (use "git add <file>..." to include in what will be committed)
>
>        ref_finder.py
>
>nothing added to commit but untracked files present (use "git add" to track)
>~~~
>{: .output}
>
>>## CHALLENGE: Add and commit your python program so that is it under version control.
>>>## Solution
>>>~~~
>>>git add ref_finder.py
>>>git commit -m "inital commit"
>>>~~~
>>>{: .language-bash}
>>{: .solution}
>We now want to make sure we have an external backup copy of our repository so lets do this on our GitHub account. <br/>
>Go to your github account and click the `Create repository` button and name your new repository. 
>>## CHALLENGE: Add a link to your new remote repository and push our Python progam to it (Use the link GitHub provides).
>>>## Solution
>>>~~~
>>>git remote add origin https://github.com/jaredraynes/Python_Prac.git
>>>git push -u origin master
>>>~~~
>>>{: .language-bash}
>>>~~~
>>>Counting objects: 3, done.
>>>Delta compression using up to 4 threads.
>>>Compressing objects: 100% (2/2), done.
>>>Writing objects: 100% (3/3), 317 bytes | 158.00 KiB/s, done.
>>>Total 3 (delta 0), reused 0 (delta 0)
>>>To https://github.com/jaredraynes/Python_Prac.git
>>> * [new branch]      master -> master
>>>Branch 'master' set up to track remote branch 'master' from 'origin'.
>>>~~~
>>>{: .output}
>>{: .solution}
{: .challenge}

## Now we are ready to start coding!!

>## Part 2 - Structure of Python Program
>>## CHALLENGE: How do we Start? Write down in words what you want your program to do.
>>>## Hint
>>>1. Read in the words in a chosen text document (text file - XML) line-by-line.
>>>2. Search the document for the words "R" and/or "Python".
>>>3. Count the number of times the words "R" and/or "Python".
>>>4. Print out the result.
>>>5. Save the result to a text document.
>>{: .solution}
>{: .challenge}
>>## CHALLENGE: Open your Python program (ref_finder.py) and start coding your program
>>>## Hint 1
>>>Import argparse and setup the argparse format.
>>{: .solution}
>>>## Hint 2
>>>Write a function.
>>{: .solution}
>>>## Hint 3
>>>Use the read command.
>>{: .solution}
>>>## Hint 4
>>>Use a for loop.
>>{: .solution}
>>>## Hint 5
>>>Use the count command.
>>{: .solution}
>>>## Hint 6
>>>Use the print command.
>>{: .solution}
>>>## Hint 7
>>>Use the write command.
>>{: .solution}
{: .challenge}