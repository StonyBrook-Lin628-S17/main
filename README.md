Computational Syntax: Playground Repository
===========================================


Overview
--------

This is the playground repository for [Computational Syntax (Lin 628)](http://lin628.thomasgraf.net), offered by the [Department of Linguistics] [department] at [Stony Brook University] [sbu].

This is a private repository where you can safely work collaboratively on the lecture notes.


Repository Structure and Workflow
---------------------------------

The repository has a number of branches:

1. *raw* contains the source code for units pulled straight from the [main repository](http://lin628.thomasgraf.net).
   Whenever a new unit is uploaded to the main repository, the student with role **master** pushes it into the *raw*-branch of this repository.
1. There is a number of feature-branches, e.g. *tikz*, *examples*, and so on.
   In each branch, one or more students work on a specific aspect of the lecture notes.
   Once they consider a task done, they file a push request against the branch *draft*.
1. The student with role **master** approves push requests and merges them into *draft*.
   He or she also compiles a pdf version of that unit.
   If compilation fails, the **master** contacts the students whose pull request created the problem and asks them to fix their code.
1. The **reader** and the **editor** read the draft version and jointly decide how to proceed: is the unit good as is, does the existing material need revisions, or is crucial material missing?
   Stylistic revisions and minor additions are handled by the editors in the *editorial* branch (with a subsequent pull request against *draft*), major changes have to be made by the students working on the relevant feature.
   (Never work directly on files in draft! It will make it much harder to resolve merge conflicts during pull requests.)
1. Once a draft version has full approval from the reader and the editor, the master merges it into the master branch.


Team Roles
----------

-  *Hammer*: quickly hammers out a rough draft that indicates the overall structure and content of the unit; this includes
    - splitting the content into sections,
    - inserting (rough versions of) definitions, theorems,
    - indicating what examples, figures and tables need to be created,
    - adding some very basic text to link all of that together.
   Imagine a bullet-point handout where complicated typesetting is left to another party.

- *Sandpaper*: takes the output produced by the hammer and sands off the rough edges; this includes
    - complete prose text as in a textbook, but without particular attention to style, spelling, or grammar
    - extending the specifications as to what needs to be added by other contributors
    - ensuring that all the Latex code up to this point is free of mistakes that prevent compilation

- *Exerciser*: thinks of exercises and adds them to the lecture notes; ideally, this student will handle all the typesetting associated with exercises, but they may ask the *artist* for help with figures

- *Solver*: writes up the solutions to all exercises; again, this student should handle all of the typesetting related to solutions on their own, though they may ask the *artist* for help with figures

- *Artist*: creates figures and trees as directed by *hammer* and *sandpaper*, but may also help the *exerciser* and *solver*; trees should be typeset with forest, figures with tikz; it is important to write clean, reusable tikz code (styles, relative node placement, foreach loops)

- *Editor*: reads the draft version produced from by team members with one of the previous 5 roles and revises it with an eye towards clarity and style

- *Reader*: reads the draft version, points out if some passages are unclear, and relays that information to the editor with suggestions for improvements

- *Master*: manages the playground repository; this means distributing files as necessary, merging in changes, ensuring that team members follow the repository policies, and helping out with git-related problems

- *Whip*: manages the workflow of the entire team; this includes
   - working out task interdependencies (e.g. a figure cannot be completed until the example has been fully specified),
   - setting deadlines for certain tasks based on these interdependencies
   - distributing the workload between team members
   - aiding communication between team members
   - anything else that is needed to keep the group working like a well-oiled machine


Role Assignments 
----------------

| Role      | Student         | 
| --:       | :--             | 
| Whip      | Hwichan         | 
| Master    | Aniello         | 
| Editor    | Jon             | 
| Reader    | Sophie          | 
| Hammer    | Jimmy, So Young | 
| Sandpaper | Jimmy, So Young | 
| Artist    | Alëna           | 
| Exerciser | Logan           | 
| Solver    | Hongchen, Lei   | 


Essential Git Commands
----------------------

-  Clone playground repository

    ~~~bash
    git clone https://github.com/CompLab-StonyBrook/mgproc.git
    ~~~

-  Get most recent version of branch <branch>

    ~~~bash
    git pull origin <branch>
    ~~~

-  Create new branch <feature>:

    ~~~bash
    git branch <feature>
    ~~~

-  Show current branch (marked by asterisk):

    ~~~bash
    git branch
    ~~~

-  Switch to branch <feature>:

    ~~~bash
    git checkout <feature>
    ~~~

-  Update current branch to the most recent commit in <branch>:

    ~~~bash
    git merge <branch>
    ~~~

   This is useful to bring in new files.

-  As before, but if there is a merge conflict, prefer our version:

    ~~~bash
    git merge -s recursive -X ours <branch>
    ~~~

   With proper workflow procedure, this makes it easy to bring in new files from *raw*.

-  As before, but if there is a merge conflict, prefer the version from the other branch:

    ~~~bash
    git merge -s recursive -X theirs <branch>
    ~~~

   Useful if a unit has been completed and you want to update all files to the revised version in master.

 
-  Stage specific files <file1>, <file2>, ..., <filen> that have been changed:

    ~~~bash
    git add <file1> <file2> ... <filen>
    ~~~

-  Stage all changed files:

    ~~~bash
    git add .
    ~~~

-  Check status of local repository:

    ~~~bash
    git status
    ~~~

-  Commit staged files:

    ~~~bash
    git commit
    ~~~

-  Pushing your changes to remote branch <feature>:

    ~~~bash
    git push origin <feature>
    ~~~


Link List
---------

### Using git

- [Github app for Windows](http://windows.github.com); supports only Windows 7 or later
- [Github app for Mac](http://mac.github.com); supports only OS X 10.9 or later
- List of alternative [GUI clients for git](http://git-scm.com/downloads/guis)
- Tutorials for using [git via the command line](https://www.atlassian.com/git/tutorials)
- Official [documentation for git](http://git-scm.com/doc)

### Markdown

- Interactive tutorial to [markdown basics](http://markdowntutorial.com/)
- [Complete markdown syntax](http://daringfireball.net/projects/markdown/syntax)
- Overview of [Github's markdown dialect](https://help.github.com/categories/writing-on-github/)

### LaTeX

- [Overleaf](https://www.overleaf.com/) (formerly writeLaTeX) is an online LaTeX editor with live preview
- List of [commonly used math symbols](http://web.ift.uib.no/Teori/KURS/WRK/TeX/symALL.html)
- Andrew Roberts' [Getting to Grips with LaTeX](http://www.andy-roberts.net/writing/latex)

### Python

- A succinct yet extensive [tutorial for Python 3](http://www.python-course.eu/python3_course.php)
- The official [Python 3 documentation](https://docs.python.org/3/)
- [Automate the Boring Stuff with Python](https://automatetheboringstuff.com/) is an excellent introduction that covers the basics of Python and applies them to real-world tasks.

[department]: http://linguistics.stonybrook.edu
[pdf]: ../../tree/master/pdf
[readings]: ../../../readings
[playground]: ../../../playground
[sbu]: http://www.stonybrook.edu
[survey]: https://testmoz.com/432409
[syllabus]: ../../blob/master/pdf/00_syllabus.pdf?raw=true
[vm]: https://drive.google.com/a/stonybrook.edu/file/d/0B09645QdWLiYUldGSGl5Tmx0Vm8/view?usp=sharing
