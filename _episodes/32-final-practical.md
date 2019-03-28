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

>>## CHALLENGE: Open a Jupyter Notebook and write code to read a text file line by line and print each line.
>>>## Solution
>>>~~~
>>>file = 'absolute file location'
>>>with open(file, "r") as f:
>>>    for line in f:
>>>        print(line)
>>>~~~
>>>{: .language-python}
>>{: .solution}
>{: .challenge}

>>## CHALLENGE: Copy your Jupyter Notebook script into a new panel and integrate a string search for 'Python' and print the number of counts.
>>>## Solution
>>>~~~
>>>file = 'absolute file location'
>>>with open(file, "r") as f:
>>>    for line in f:
>>>        if line.string("Python") == True:
>>>            count += 1
>>>        print("Python was found", count, "times")
>>>~~~
>>>{: .language-python}
>>{: .solution}
>{: .challenge}

>>## CHALLENGE: In a new panel in your Jupyter Notebook, turn your script into a reusable function.
>>>## Solution
>>>~~~
>>>def ref_finder(file_location):
>>>
>>>    file = file_location
>>>    with open(file, "r") as f:
>>>        for line in f:
>>>            if line.find("Python") == True:
>>>                count += 1
>>>            print("Python was found", count, "times")
>>>~~~
>>>{: .language-python}
>>{: .solution}
>{: .challenge}

>>## CHALLENGE: Copy your function into your ref_finder.py program and integrate Argparse so that your program can accept any file from the command line.
>>>## Solution
>>>~~~
>>>import argparse
>>>
>>>def ref_finder(file_location):
>>>
>>>    file = file_location
>>>    with open(file, "r") as f:
>>>        for line in f:
>>>            if line.find("Python") == True:
>>>                count += 1
>>>            print("Python was found", count, "times")
>>>
>>>parser = argparse.ArgumentParser()
>>>parser.add_argument("file_location")
>>>args = parser.parse_args()
>>>ref_finder(args.file_location)
>>>~~~
>>>{: .language-python}
>>{: .solution}
>{: .challenge}

>>## CHALLENGE: Update your ref_finder.py program to include optional arguments so you can search for references to 'R' or 'Python.
>>>## Solution
>>>~~~
>>>import argparse
>>>
>>>def ref_finder(file_location, language):
>>>
>>>    file = file_location
>>>    string = language
>>>    with open(file, "r") as f:
>>>        for line in f:
>>>            if line.find(string) == True:
>>>                count += 1
>>>            print(string, "was found", count, "times")
>>>
>>>parser = argparse.ArgumentParser()
>>>parser.add_argument("file_location")
>>>parser.add_argument("language")
>>>args = parser.parse_args()
>>>ref_finder(args.file_location, args.language)
>>>~~~
>>>{: .language-python}
>>{: .solution}
>{: .challenge}

>>## CHALLENGE: Update your ref_finder.py program so that it can search for both 'R' and 'Python' as an optional argument, printing the counts for both.
>>>## Solution
>>>~~~
>>>import argparse
>>>
>>>def ref_finder(file_location, language, count_both):
>>>
>>>    file = file_location
>>>    if both == True:
>>>        string1 = 'R'
>>>        string2 = 'Python'
>>>        with open(file, "r") as f:
>>>        for line in f:
>>>            if line.find(string1) == True:
>>>                R_count += 1
>>>            if line.find(string2) == True:
>>>                Py_count += 1
>>>            print(string1, "was found", R_count, "times")
>>>            print(string2, "was found", Py_count, "times")
>>>    else:
>>>        string = language
>>>        with open(file, "r") as f:
>>>            for line in f:
>>>                if line.find(string) == True:
>>>                    count += 1
>>>                print("string", "was found", count, "times")
>>>
>>>parser = argparse.ArgumentParser()
>>>parser.add_argument("file_location")
>>>parser.add_argument("language")
>>>parser.add_argument("-b", "--count_both", default = False)
>>>args = parser.parse_args()
>>>ref_finder(args.file_location, args.language, args.count_both)
>>>~~~
>>>{: .language-python}
>>{: .solution}
>{: .challenge}