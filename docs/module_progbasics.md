# Programming Basics questions

## Computer science

### Data structures

#### What is the purpose of a list (array in some programming languages) data structure? Name some methods of it! 
A list is a collection of items ordered in an indexed array. 
Methods: clear(), index(), count(), sort(), reverse(), remove(), pop(), insert(), append()

#### What is the difference between a list/array and a set?
A set is unordered and unindexed and doesn't allow duplicates. A list is ordered and changeable.

#### What is the purpose and methods of a dictionary/map data structure?
A dictionary is an unordered collection of data key:value pairs. (you can store data values like map)
Methods: values(), keys(), pop(), update(), get(), items(), clear()

### Algorithms

#### Fibonacci sequences. Write a method (or pseudo code), that generates the Fibonacci sequences.
``` python
def fib(n): #number of Fibonacci numbers
    i = 0
    j = 1
    k = 0
    fib = []   
    for i in range(0,n):       
        fib.append(j+k)
        j = k
        k = fib[i]
    return fib
```
#### How do you find a max value in a list/array if you can’t use any built-in functions?
We set a variable max = 0, we iterate in the list and for each value greater than max, max = value, at the end of the iteration we will have the max of the list

#### How do you find the average of values in a list/array if you can’t use any built-in functions?
Similar with the max, we will find the minimum, the add min with max and divide by the length of the list

#### What do we call an *in-place* sort?
A sort algorithm in which the sorted items occupy the same storage as the original ones.
In-place sorting means sorting without any extra space requirement, an in-place algorithm is an algorithm which transforms input using a data structure with a small, constant amount of extra storage space. Quicksort is one example of In-Place Sorting.

#### Explain an algorithm which sorts a list!
Bubble Sort Algorithm is used to arrange N elements in ascending order, and for that, you have to begin with 0th element and compare it with the first element. If the 0th element is found greater than the 1st element, then the swapping operation will be performed, i.e., the two values will get interchanged. In this way, all the elements of the array get compared.


### Programming paradigms - procedural

#### What is the call stack?
A call stack is used for several related purposes, but the main reason for having one is to keep track of the point to which each active subroutine should return control when it finishes executing. The primary purpose of a call stack is to store the return addresses. When a subroutine is called, the location (address) of the instruction at which the calling routine can later resume needs to be saved somewhere.

#### What is “Stack overflow”?
A stack overflow is an undesirable condition in which a particular computer program tries to use more memory space than the call stack has available.

#### What are the main parts of a function?
Keyword def marks the start of function header.
A function name to uniquely identify it. Function naming follows the same rules of writing identifiers in Python.
Parameters (arguments) through which we pass values to a function. They are optional.
A colon (:) to mark the end of function header.
Optional documentation string (docstring) to describe what the function does.
One or more valid python statements that make up the function body. Statements must have same indentation level (usually 4 spaces).
An optional return statement to return a value from the function.

### Programming languages - Python  
#### How do you use a dictionary in Python?
Use {} curly brackets to construct the dictionary, and [] square brackets to index it. Separate the key and value with colons : and with commas , between each pair. Keys must be quoted. As with lists we can print out the dictionary by printing the reference to it. A dictionary maps a set of objects (keys) to another set of objects (values). A Python dictionary is a mapping of unique keys to values. Dictionaries are mutable, which means they can be changed. The values that the keys point to can be any Python value. Dictionaries are unordered, so the order that the keys are added doesn't necessarily reflect what order they may be reported back.

#### What does it mean that an object is immutable in Python?
It means that after you create the object and assign some value to it, you can't modify that value.

#### What is conditional expression in Python?
Evaluates something based on a condition being True or False.

#### What are different types of arguments in Python?
Default arguments, required arguments, keyword arguments, variable number of arguments.

#### What is variable shadowing? (context: variable scope)
Occurs when a variable declared within a certain scope (decision block, method, or inner class) has the same name as a variable declared in an outer scope.

#### What can happen if you try to delete/drop/add an item from a List, while you are iterating over it in Python?
We would have an IndexError

#### What is the "golden rule" of variable scoping in Python (context: LEGB)? What is the lifetime of variables?
The golden rule of programming is make your code as concise as possible. Functions enable you to reach that goal by enabling you to avoid rewriting the same piece of code multiple times within your program. Functions allow you to define a set of commands at the beginning of a program and reuse it many times later on with only one line of code. 
The lifetime of a variable is the time during which the variable stays in memory and is therefore accessible during program execution. The variables that are local to a method are created the moment the method is activated (exactly as formal parameters) and are destroyed when the activation of the method terminates.

#### If you need to access the iterator variable after a for loop, how would you do it in Python?
Return i?

#### What type of elements can a list contain in Python?
A list can contain nested lists, strings, numbers, booleans, characters.

#### What is slice operator in Python and how to use?
slice(start, stop, step)

#### What arithmetic operators (+,*,-,/) can be used on lists in Python? What do they do?
All 4 and they will add, multiply, substract and divide elements of a list. You can also add one list with another.

#### What is the purpose of the in and not in membership operators in Python?
in – evaluates to True if the value in the left operand appears in the sequence found in the right operand. 
not in – evaluates to True if the value in the left operand doesn't appear in the sequence found in the right operand.

#### What does the + operator mean when used with strings in Python?
Concatenation

#### Explain f strings in Python?
Every f-string statement consists of two parts, one is character f or F, and the next one is a string which we want to format. The string will be enclosed in single, double, or triple quotes.
In place of string, we have to place our sentence which is going to format.

#### Name 4 iterable types in Python!
list, dictionary, string, tuple

#### What is the difference between list/set/dictionary comprehension and a generator expression in Python?
The difference between the two kinds of expressions is that the List comprehension is enclosed in square brackets [] while the Generator expression is enclosed in plain parentheses ()
The list/set/dictionary comprehension is easier to write and read and executes immediately.

#### Does the order of the function definitions matter in Python? Why?
It matters, if you need to call a function in another function, then the function to be called needs to be defined before.
At the end function main will contain all the functions defined in the program.

#### What does unpacking mean in Python?
We can unpack tuple values into variables. 
name, age = a
In Python there is a very powerful tuple assignment feature that assigns right hand side of values into left hand side. In other way it is called unpacking of a tuple of values into a variable. 
Python uses a special syntax to pass optional arguments (*args) for tuple unpacking. This means that there can be many number of arguments in place of (*args) in python. All values will be assigned to every variable on left hand side and all remaining values will be assigned to *args .

#### What happens when you try to assign the result of a function which has no return statement to a variable in Python?
Variable will become None

## Software engineering

### Debugging

#### What techniques can you use while debugging a program in Python?
Rubber duck, print/trace debugging, debugger

#### What does step over, step into and step out mean while using the debugger?
Step over a line or function, step into the program, step out - quit the debugger

#### How can you start to debug a program from a certain line using the debugger?
Using a breakpoint

### Version control

#### What are the advantages of using a version control system?
The same advantages you get of using version control for any other kind of documents. Helps for many people to collaborate on a single document/project, keeps track of all the changes to the document as it evolves, you can revert and/or merge edits. Version control systems also let you work on several machines.

#### What is the difference between the working directory, the staging area and the repository in git?
The working directory is a single checkout of one version of the project. This essentially means if you checkout a branch (e.g. master) and are sat on a particular commit (e.g. HEAD), your working directory is the "umbrella" term for all your files and folders.
Staging area is files that are going to be a part of the next commit, which lets git know what changes in the file are going to occur for the next commit. The repository contains all of a project's commits.

#### What are remote repositories in git?
A remote in Git is a common repository that all team members use to exchange their changes. In most cases, such a remote repository is stored on a code hosting service like GitHub or on an internal server. In contrast to a local repository, a remote typically does not provide a file tree of the project's current state.

#### Why does a merge conflict occur?
A merge conflict happens when two branches both modify the same region of a file and are subsequently merged. Git can't know which of the changes to keep, and thus needs human intervention to resolve the conflict.

#### Through what series of commands could you put a new file into a remote repository connected to your existing local repository?
git status, git add . , git commit -m "", git push

#### What does it mean atomic commits and descriptive commit messages?
It's important for the commits to be atomic: a commit should do one thing at a time. If you are making several changes, split them into separate commits.

Separate subject from body with a blank line
Limit the subject line to 50 characters
Capitalize the subject line
Do not end the subject line with a period
Use the imperative mood in the subject line
Wrap the body at 72 characters
Use the body to explain what and why vs. how

#### What’s the difference between git and GitHub?
The key difference between Git and GitHub is that Git is an open-source tool developers install locally to manage source code, while GitHub is an online service to which developers who use Git can connect and upload or download resources.

## Software design

### Clean code

#### What does clean code mean?
You usually write code. This act implies somebody will read it later. The reader can be your pair-programming partner, your teammate, your boss, any open source contributors, etc. Even if your code is read only by the computer, you might have to build on it later so that you will be the reader. Even if you don't plan to read it in the future, your incentive should be to write clean code which is not only pleasant to read but also simple to build upon.
No magic numbers, good naming, no repetitions or duplicates, no useless code

#### What steps do we usually do during a clean code refactoring?
ad through the whole code
Summarize what is the purpose of the script in one sentence.
Run the code to see what is the end result
The code should keep runnable and show the same content when you finish the refactor
Do not forget to run the code frequently to check you are on the right track
Removing: clutter (format code, delete comments), complexity(bad names, long methods, deep conditionals, magic numbers), cleverness (as opposed to simple and elegant), duplicates

### Error handling

#### What is exception handling?
Exception handling is the process of responding to exceptions when a computer program runs. An exception occurs when an unexpected event happens that requires special processing

#### What are the basics of exception handling in Python?
To use exception handling in Python, you first need to have a catch-all except clause. The words "try" and "except" are Python keywords and are used to catch exceptions.

#### In which case should we catch an exception? Why?
We want to catch an exception so that we can continue out program instead of it crashing.

#### What can/should we do with an exception in the ‘except’ block?
Print a message

#### What does the else and finally statement do in a try-except block in Python?
In the try clause, all statements are executed until an exception is encountered. except is used to catch and handle the exception(s) that are encountered in the try clause. else lets you code sections that should run only when no exceptions are encountered in the try clause. Finnaly will execute no matter what

## Software Development Methodologies

#### What is the main goal of a retrospective meeting?
The goal of the retrospective is for the team members to discuss among themselves about how the work went during the last sprint so that better ways can be found to meet the project's goals. 

## Programming environment

### Unix

#### What is UNIX and what is Linux?
Unix is an operating system. It supports multi-tasking and multi-user functionality. Unix is most widely used in all forms of computing systems such as desktop, laptop, and servers. On Unix, there is a Graphical user interface similar to windows that support easy navigation and support environment.
Linux is the best-known and most-used open source operating system. As an operating system, Linux is software that sits underneath all of the other software on a computer, receiving requests from those programs and relaying these requests to the computer's hardware.

#### What do we call the shell in Linux?
Bash

The shell is the command interpretor in an operating system such as Unix or GNU/Linux, it is a program that executes other programs. It provides a computer user an interface to the Unix/GNU Linux system so that the user can run different commands or utilities/tools with some input data

#### What does root means in a Linux environment?
Root is the user name or account that by default has access to all commands and files on a Linux or other Unix-like operating system. It is also referred to as the root account, root user and the superuser.

#### How do you access your personal files in Linux?
Right at the top of the tree is the root folder, referred to as /. Inside this folder are a number of special system folders, each with a specific use. As an example, the /home folder contains a number of home directories for each user on the system. As such, the user account has the home folder set to /home/matthew.

#### How can you install an application in Linux?
The most common method of installing apps from the command line is through software repositories (a place where software is stored) using what's called a package manager. All Linux apps are distributed as packages, which are nothing more than files associated with a package management system. Every Linux distribution comes with a package management system, but they are not all the same.

#### What is package management in Linux, what are repositories?
A package management system is comprised of sets of tools and file formats that are used together to install, update, and uninstall Linux apps. The two most common package management systems are from Red Hat and Debian. Red Hat, CentOS, and Fedora all use the rpm system (.rpm files), while Debian, Ubuntu, Mint, and Ubuntu use dpkg (.deb files). Gentoo Linux uses a system called Portage, and Arch Linux uses nothing but tarballs (.tar files). The primary difference between these systems is how they install and maintain apps.
A software repository, or “repo” for short, is a storage location where software packages are stored and retrieved. A software repository is typically managed by source control or repository managers. Package Managers allow for installing and updating the repositories (sometimes called “packages”) versus having to manually do this.

#### How do you navigate in the filesystem with the command line?
pwd, ls, cd

#### What does the following commands do: mkdir, rm, cat, cp, touch?
make directory, remove, cat : reads data from the file and gives their content as output, copy files or group of files in dir, touch - create, change and modify a file
#### How can you look up what does a command do in Linux if you have no internet connection?
--help

#### What does the following commands do: head, tail, more, less?
By default head returns the first ten lines of each file that it is given.
By default tail returns the last ten lines of each file that it is given. It may also be used to follow a file in real-time and watch as new lines are written to it.
More is a command to view the contents of a text file one screen at a time.
It is similar to more, but has the extended capability of allowing both forward and backward navigation through the file

#### How do you download a file from internet using the terminal?
Using the curl command and the url