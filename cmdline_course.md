---
layout: default
---

## Introduction
Command Line Tools for Linguists is an introductory course to the Linux/Unix environment. The course consists of the universally useful fundamentals of the Unix command line (navigating the command line, running and installing programs, writing scripts, using version control) as well as some tools specifically useful in language technology (regular expression and corpus processing).


## Week 1: Introduction to Command Line Environments
The course started with setting up the command line environment on our own computers. Once everything was set up, some basic Unix command line tools were introduced. These tools could be roughly split into two categories: navigating directories and handling (text) files. For example, we learned the command `cd`:   
```
cd my_dir
```  
which changes the current directory to the one given as its argument. Additionally, we installed `wget` and used it to fetch text files from websites.
Here's a list of the commands introduced during the first week:
* ls
* pwd
* whoami
* wget
* mv
* cat
* less
* cp
* rm
* mkdir
* cd
* emacs

I had very little to no former experience of working in the command line so everything we learned was new to me. Regardless, I felt like I got the gist of the basic commands fairly quickly as the videos were quite informative and appropriately paced. I had no clue that text editors even existed in the command line and emacs turns out to be very different from Word so I struggled a bit with all the new shortcuts there were to learn.

## Week 2: Navigating a UNIX System
The second week continued with the theme of navigation from the first week. In the first week, we learned to move, copy and remove files and this week we applied those commands to directories as well. Another theme was processes and how they can be managed in the foreground and background. For example, if one wants to view all running processes, the suitable command would be:
```
ps aux
```
We also learned how to kill processes using the process ID. The last major theme of the week was working in remote servers. We used `ssh` to connect to a remote server and `scp` to copy files to and from remote servers. Again, all this was new information to me but I felt like I got a better hold of the basic commands such as `cd` and `ls`.


## Week 3: Basic Corpus Processing
Week 3 started with learning about different character encodings such as ASCII and UTF-8. In addition to learning what these are, we learned to view and change the encoding of a file. We continued with some fundamental text processing commands such as `tr`, `sort`, `uniq`, and `wc`. These commands were then applied to some text documents to demonstrate some corpus processing tools found in the command line. Regular expressions and `grep` (as well as `egrep`) were also briefly introduced. For example, if one wants to find all lines with the letter sequence "exp" or "Exp" in it, a possible command could look like this:
```
egrep "[Ee]xp" myfile.txt
```

Here's a table with some useful `grep` options:

| *`grep` option* | *Description*                                      |
|-----------------|----------------------------------------------------|
| -c              | Output the number of lines where a match is found. |
| -a              | Treat all files a ASCII text.                      |
| -i              | Ignore letter case.                                |
| -o              | Print only the matching parts of lines.            |
| -v              | Invert match.                                      |
| -n              | Print the line number before every match.          |

The final topic of the week was formatted text files such as csv and tsv as well as commands useful in processing such files (`cut` and `paste`). I was already somewhat familiar with quite many of this week's topics (regex and `grep`) but there was still much to learn. I had a very vague idea about csv-files despite having seen them before in many different contexts and this week's content helped me understand what they're about.

## Week 4: Advanced Corpus Processing
Continuing the theme of text processing tools, week 4 introduced `sed`. It is quite a powerful tool for tasks that involve matching, deleting and replacing strings or lines containing those strings. For example, if one wants to find all occurrences of the string "sad" in a file and replace them with "happy", a following command would do the trick:
```
sed 's/sad/happy/g' myfile.txt
```
In this example, the 's' means that the command substitutes a string with something else. The 'g' makes it so `sed` substitutes the strings globally. If the 'g' is omitted, only the first occurrence in each line is substituted with the new string. `sed` is not something I was familiar with from before so I had my fair share of difficulties with it. I still don't feel too confident with it but knowing such tool exists will definitely prove useful in the future.

The other main topic of the week was pipelines. Pipelines allow for the chaining of multiple commands in order to, for example, perform some more demanding corpus processing tasks on a text file. In the exercises we created copies of books in a sentence-per-line -format as well as transformed files into lists of n-grams and word frequency lists. In addition to the two main topics of `sed` and pipelines, we continued practising regular expressions as those are a big part of what makes `sed` so useful.


## Week 5: Scripting and Configuration Files
The fifth week picked up where the fourth ended as the next step was to make the long pipeline commands into a tidy script. Using scripts it is possible to gather a long sequence of commands into one file and simply execute the file as if it were a program. When writing bash scripts, it is possible to make conditions with if-statements and repeat commands with for-loops (just like in any other programming language).

We also took a look at configuration files and what one can do by changing the variables found in it. These include changing the appearance of the command prompt, adding directories to the PATH-variable and changing the locale settings, among many, many other things. We also learned how to make aliases which can act as useful shortcuts when, for example, trying to access directories quickly without having to type out the entire path. Here's an example of an alias I added to my bash configuration file to make my workflow a bit more efficient during the course:
```
alias kik='cd ~/KIK-LG219'
```
Below is another alias created by a reddit user. That one should probably be left untouched.
![alias_meme](https://i.redd.it/gaxh9l90mzaz.png "Do not try this at home")  
*A Unix user's worst nightmare, posted on [reddit](https://www.reddit.com/r/ProgrammerHumor/comments/6opquz/the_worst_nightmare_for_a_unix_user/)*

## Week 6: Installing and Running Programs
This week revolved around installation of software and the different commands that can be used to achieve that. Package managers like `apt-get` and homebrew were introduced. Although we had already been using them before during the course, this week's material explained how they take care of software dependencies. To install python libraries and packages from outside of the standard Python library we learned to use `pip` (or `pip3`). This was something I had already been using during my previous studies but I didn't have a slightest idea what `pip` actually was before reading the material. Using `pip` we installed some Python packages to use in the exercises. Here's a command I've been using quite a lot:
```
pip install nltk
```
This command installs the Natural Language Toolkit which I've been frequently using in my language technology studies.

The second theme of the week was `make`. This topic expanded even further into the task of automating complicated sets of commands for multiple files. Whereas scripts can be used for storing long pipeline commands and executing them on files, `make` can be used for storing multiple scripts and executing them on a collection of files. We learned some simple rules and variables that can be used in the Makefile. `make` was totally new to me and the syntax used in the Makefile took some getting used to. However, it was interesting to see how easy it made executing multiple scripts for a set of text files in our corpus processing exercise. 

## Week 7: Version Control  
The final theme of the course was version control with Git. Git is used for tracking the changes made to files when working on a project (such as this one) which makes it rather easy to go back to a previous version if needed or to track changes that other people have made when working remotely on a collaborative project. Here's a set of essential commands which any Git user is familiar with:
```
git status
git add .
git commit -m "Informative message about the commit (or some random gibberish, depends)."
git push origin master
```
Again, Git and GitHub were both familiar words to me, but I had no real knowledge of what either of them are. This week's material helped me add one of my earlier projects to GitHub, which is something I've been meaning to do for a long time but just postponed repeatedly.

Other topics introduced in the last week were Jekyll and GitHub pages, both of which tie in with this project. Jekyll can be used to create a static website based on text files written in some markup language (I'm using Markdown). The site can then be reviewed by running the command:
```
bundle exec jekyll serve
```
Learning to create a github.io site has been a fun task. Being familiar with Markdown (from writing Reddit comments and posts :-D) was very helpful in this project. Overall, this course felt like a big "Aha!" experience; so many of the introduced concepts were things I was aware of but hadn't actually used before.