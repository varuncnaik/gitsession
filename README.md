# CS 368 (C++) Fall 2016 Git/GitHub session

This is a test repository for the CS 368 Git/GitHub session.
To clone this repo, run:

    $ git clone git@github.com:varuncnaik/gitsession.git

## Commands

These are the commands we ran during the session. Feel free to run
them yourself to create a new local repo, and push it to GitHub. I
have added some comments for clarity.

To create a local repository ("local repo" for short):

    $ mkdir gitsession/
    $ cd gitsession/
    $ git init
    $ git status

To create your first commit:

    $ vim hello.cpp
    $ g++ -std=c++11 hello.cpp
    $ ./a.out
    $ rm a.out
    $ git commit -m "Initial commit"  # Oops
    $ git add hello.cpp
    $ git status
    $ git commit -m "Initial commit"  # Success!
    $ git status
    $ git log

To create your second commit:

    $ vim hello.cpp
    $ g++ -std=c++11 hello.cpp
    $ ./a.out
    $ git status
    $ git diff
    $ git add hello.cpp
    $ git status
    $ git diff                        # Oops
    $ git diff --staged               # Success!
    $ git commit -m "Changed output message"
    $ git status
    $ git log

To push to an empty remote repository ("remote repo") on GitHub:

    $ git remote add origin git@github.com:<username>/<reponame>.git
    $ git push -u origin master

To copy your code (and history) on a new machine, and push a commit:

    $ git clone git@github.com:<username>/<reponame>.git
    $ cd <reponame>
    $ git status
    $ git log
    $ vim README.md
    $ git status
    $ git add README.md
    $ git diff --staged
    $ git commit -m "Added README"
    $ git push -u origin master

To pull your changes onto the original machine:

    $ git pull origin master
    $ git log

To unstage a file:

    $ git add a.out                   # Oops
    $ git status
    $ git reset HEAD -- a.out         # Fixed
    $ git status

To remove the last commit:

    $ git add a.out                   # Oops
    $ git commit -m "Bad commit"      # Double oops
    $ git log
    $ git reset HEAD~1                # Fixed!
    $ git log

## More information

To learn more about git, see https://git-scm.com/book/en/v2
