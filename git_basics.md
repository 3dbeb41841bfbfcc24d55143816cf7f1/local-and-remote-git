# Introduction to Version Control with GIT
(90 minutes)

## Learning Objectives - IWBAT
### Concepts
* Explain what Version Control is
* List the problems that Version Control solves
* List the main components of a git repository and how they relate:
    - repository
    - working area
    - index / stage
    - commit
    - head

### Skills
* Create a local git repository
* Add and commit changes to a git repository
* Check the status of a git repository
* View the history of a git repository
* Checkout an old version of the repo

## Why Version Control?

### Pair & Share
* Spend a few minutes discussing the following questions:
  Assuming that version control systems did not exist, how would you:
    - Share your source code with other developers?
    - Collaborate with other developers
    - Support multiple versions of a software product?
        - Free vs. Paid
        - Basic vs. Premium
        - 2.x vs. 3.x

## What is Version Control?
* _Version Control_ is the management of changes to documents, computer
programs, web sites, and other collections of information.

* _Version Control_ provides:
    - a database containing a history of changes to a set of files
    - a set of commands for managing that database

## What is Version Control Good For?
* Manage Changes Over Time
    - Save various points in the development of your work.
    - See the history of your work.
    - Go "Back In Time" to see previous versions of your work.
    - Manage multiple versions of a software project.
* Sharing & Collaboration
    - Share your work with others.
    - Work effectively as a team on a single project.
    - Allow others to modify your work in a controlled way.
    - Make multiple changes to a project in parallel.
    - Merge parallel changes in a controlled way.
* Experimentation
    - Experiment with various ideas and either keep or discard your experiments.
    - Keep multiple changes isolated until they are ready to be integrated.

## Code Along
(about 40 minutes)

### Agenda
* Check our GIT configuration
* Develop our GIT Skills
  - Create a Local GIT repo
  - Add files
  - Make commits
  - Check the repo status
  - View history
  - Time travel

### Code Along Part 1 - Setup

Check the GIT Version:

    $ which git
    $ git --version

Check your GIT Config:

    $ git config --list
    $ git config user.name

Set your identity:

    $ git config --global user.name "John Doe"
    $ git config --global user.email johndoe@example.com

Set your default editor:

    $ git config --global core.editor "subl -n -w"

### Code Along Part 2 - Creating a repo

Create a new local GIT repository:
    $ cd ~/wdi/projects/git
    $ mkdir sample1
    $ cd sample1
    $ git init

* What just happened?
* Did your Shell Prompt change?

### Code Along Part 3 - Our first commit

Add some files:
    $ touch README.md hello.rb
    $ git status
    # What is an untracked file?

    $ git add .
    $ git status
    # Now the files are in the stage

Commit the changes:
    $ git commit -m "Added 2 files."
    $ git status
    $ git log

##### On the whiteboard, draw a diagram of the following:
* working area
* stage
* git repository (.git)

[diagram1](http://thkoch2001.github.io/whygitisbetter/images/index1.png)
[diagram2](http://i.stack.imgur.com/YSVtk.png)

### Code Along Part 4 - More commits, viewing the history

Edit hello.rb and commit changes:

    # Modify a file
    $ echo "puts 'Hello, World'" >> hello.rb
    $ git status
    # We now see a "modified" file, but nothing is staged.

    # Let's add our changes to the stage
    $ git add .
    $ git status

    # Now our changes are staged and we can do a commit
    $ git commit -m "Fixed hello.rb"

    # Let's view the repo history
    $ git log

    # Notice all of the info in the log
    # In what order are the commits displayed?

## Code Challenge - Make additional changes and commits

* Check your status and history as you go
* Suggested changes:
    - Hello General Assembly
    - Hello WDI
    - Hello GIT

Instructor Demos Solution

### Code Along Part 5 - Cherry Picking

Demo the editing of multiple files but only adding one of them to the stage

    $ git add file1
    $ git commit
    $ git status
    $ git log

### Code Along Part 6 - Checking out a Previous Version

    $ git log
    $ git checkout hash_of_previous_commit
    $ cat hello.rb
    # We see the old version

    # Let's look at the history
    $ git log
    # By default the log command only shows up to the current commit we are on

    # Let's see all of the commits
    $ git log --all --decorate
    # What is HEAD and master?

    # Now let's get back to the most recent version
    # We have a few ways to do this:
    $ git checkout master
        or
    $ git checkout hash_of_most_recent_commit

### Code Along Part 7 - Diffing

    # View unstaged differences
    $ git diff
        or
    $ git diff filename

    # View staged differences
    $ git diff --staged
        or
    $ git diff --staged filename

### Code Along Part 8 - Rolling back changes

    # unstage changes to a file
    $ git reset filename
    $ git status

    # Discarding changes (reverting to the committed version)
    $ git checkout filename
    $ git status

## Review

* Can someone tell me what a GIT Repository is?
* What are some key components of a GIT repo?
* Can someone describe an important GIT command (get several responses from
  students)

## Q & A

## Homework

* There is no homework for this lesson. Students will soon be using GIT and
  GitHub to submit their homework thus giving them plenty of experience with
  GIT.

## Quiz

1. What is the GIT command for creating a new database from the terminal?

2. When you first edit and save a file, the changes are stored in:
  * a. the stage
  * b. the .git directory
  * c. the working area

3. A GIT commit will include all of the changes that are in the:
  * a. the stage
  * b. the .git directory
  * c. the working area

4. What command would you use to add the changes to the file "hello.rb" to the stage?

5. What GIT command is used to load a previous revision into the working area?

### Quiz Answers

1. init
2. (c) the working area
3. (a) the stage
4. git add hello.rb
5. checkout
