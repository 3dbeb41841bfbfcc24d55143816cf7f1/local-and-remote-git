# Branching with GIT
(60 minutes)

## Learning Objectives

### Concepts
* Describe how GIT commits are connected
* Describe GIT tags and the HEAD
* Describe branching & merging
* List scenarios where creating a branch is beneficial

### Skills
* Create a new branch
* Switch to a branch and add commits to it
* Merge branches together
* View the history

## What is Branching

Branching provides a way to manage multiple, independent paths of changes.

* A branch creates an alternate path for making changes and commits
* Changes in the branch are isolated from the main line (master) branch
* You can create as many branches as you want
* Branches can be:
    - shared or kept private
    - merged
    - deleted

## Code Along Part 1 - Create a branch and commit to it

For this code along we will continue to use the GIT repo we created from
the "GIT Basics" Code Along.

Go to the git repo folder:

    $ cd ~/wdi/projects/git/sample1

Let's make sure the repo is _clean_:

    $ git status

Let's take another look at the history:

    $ git log

Let's display a list of all of the branches:

    $ git branch

Let's create a new branch:

    $ git branch friendly_greeting
    $ git branch

You should now see the new branch in the list

Checkout out the new branch:

    $ git checkout friendly_greeting

Did your prompt change?

Edit hello.rb and view the status:

    $ git status

### Ask class: How do we save this change as a commit?

    $ git add .
    $ git commit -m "Added a friendly greeting"
    $ git status

View the history:

    $ git log

## Code Along Part 2 - Add a new file to branch

    $ touch file2.txt
    $ git status
    $ git add .
    $ git status
    $ git commit -m "Added file2.txt"
    $ git status
    $ git log

## Code Along Part 3 - Switch to master and then back to branch

    $ git checkout master
    $ cat hello.rb

Note the older version of hello.rb

    $ ls
Note that file2.txt does not exist in this branch

    $ git checkout friendly_greeting
    $ ls

Note that we have file2.txt again

    $ ruby hello.rb

and we have our friendly greeting

## Code Along Part 4 - Merge branch into master

    $ git checkout master
    $ git log --all --decorate

We will use that log command a lot so let's create an alias for it:

    $ git alias h "log --all --decorate"
    $ git h

Note the log output as it's about to get more interesting

Now let's do the merge:

    $ git merge friendly_greeting

The merge command merges the specified branch into the current one.

    $ git h

Notice where the *HEAD*, *master*, and *friendly_greeting* markers are at

## Short Lab - Create Another Branch
(15 minutes)

* Create a branch called *with_time*
* After the greeting, print the current time using *Time.now*
* Test your code
* Commit it
* Merge the *with_time* branch into the master

Solution for greeting with time:

    puts "Hello World"
    current_time = Time.now
    puts "The time is now #{current_time}"

## Review Lab

## Final Thoughts

* At this point we can continue to work in any of the branches
* We can delete a branch when it is no longer needed
* We can merge any branch into any other branch
* Branches can be shared with other developers (more on this when we get to GitHub)

## Review

* Can someone explain the benefits of branching?
* Give some reasons for creating a branch

## Q & A

## Homework

* There is no homework for this lesson. Students will soon be using GIT and
  GitHub to submit their homework thus giving them plenty of experience with
  GIT.

## Quiz

1. How would you create a new branch with the label "ask_user"?

    A: git branch ask_user

2. What is the GIT command for switching to a branch with the name "ask_user"?

    A: git checkout ask_user

3. What is the GIT command for listing all of the branches

    A: git branch

4. If you are currently working in the ask_user branch, what command(s) would
   you use to merge the "ask_user" branch into the master branch?

    A:
      git checkout master
      git merge ask_user
