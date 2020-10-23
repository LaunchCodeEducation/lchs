Repositories and Commits
=========================

To use all of the tools and benefits of Git, we need to set up a repository for
each new project we create. Once we do that, the next step is learning how to
save and track our changes.

Create a Repository
-------------------

To start adding content to a git repository, we must first create one. We will
use Visual Studio Code, the terminal, and a series of commands to do this.

.. index::
   single: git; repository
   single: git; repo

.. admonition:: Try It!

   Follow these steps to create your first git repository (called a **repo**
   for short).

   #. Launch Visual Studio Code and open the ``local_practice`` folder you
      created in the last chapter.
   #. Use the buttons in the File Explorer to create a new directory called
      ``git_practice``.

      .. figure:: figures/git-init-filetree.png
         :alt: VS Code file tree showing the new git_practice directory.

         Our new file tree for local_practice.

   #. Open the terminal panel if it's not already there. Use it to navigate
      into the new ``git_practice`` directory.

      .. sourcecode:: bash
         :linenos:

         $ pwd
         /Users/username/Desktop/local_practice
         $ ls
         git_practice   hello.py   hello_web   module_practice   turtle_fun.py
         $ cd git_practice
         $ pwd
         /Users/username/Desktop/local_practice/git_practice

   #. Finally, initialize the new repository with the command ``git init``.

      .. sourcecode:: bash
         :lineno-start: 6

         $ pwd
         /Users/username/Desktop/local_practice/git_practice
         $ git init
            Initialized empty Git repository in /Users/username/Desktop/local_practice/git_practice/.git

We are now set up to have Git track all changes made inside the
``git_practice`` folder.

Let's add some code and see how to track our project!

Making Commits
--------------

Right now, ``git_practice`` is empty. However, the version control has already
begun keeping track of the directory. We can see this by trying out our second
git command in the terminal:

.. sourcecode:: bash
   :linenos:

   $ git status
   On branch master

   No commits yet

   nothing to commit \(create/copy files and use "git add" to track\)

We will deal with ``On branch master`` later in this chapter, but the next two
lines deserve some attention.

.. index:: ! commit

.. index::
   single: git; commit

Line 4 tells us that we have made no **commits** yet. A commit is a saved
change recorded in the repo. If we think of the repository as a container, then
the commits are smaller containers stacked on top of each other inside the
repo. Each commit includes a time stamp and a copy of all the files as they
existed at that time. The more we dig down inside a repository, the farther
back in time we go.

Line 6 tells us, *Hey, if you want to track your project, you need to put
something in this directory!*

Let's add a new file to the ``git_practice`` folder and then make our first
commit.

Lorem ipsum...

After a while, the programmer has made a lot of changes and saved their code
files many times over.
So when do they make a commit to their repository?

.. admonition:: Tip

   The general rule of thumb is that any time a significant change is made to
   the code, a commit should be made.

If the programmer has created the Git repository and is ready to commit, they can do so by following the commit process.

.. admonition:: Note

   Git does have a simple commit command, however, making a proper commit requires that the programmers follow a longer procedure than just one command.

The procedure for making a commit to a Git repository includes 4 stages.

1. ``git status`` gives the programmer information about files that have been changed.
2. ``git add`` allows the programmers to add specific or all changed files to a commit.
3. ``git commit`` creates the new commit with the files that the programmer added.
4. ``git log`` displays a log of every commit in the repository.

If the steps above are followed correctly, the programmer will find their latest commit at the top of the log.

Here is how the process will look in the terminal:

::

   Students-Computer:homework student$ git status
   On branch master

   Initial commit

   Untracked files:
     (use "git add <file>..." to include in what will be committed)

         learning-git.js

   nothing added to commit but untracked files present (use "git add" to track)
   Students-Computer:homework student$ git add .
   Students-Computer:homework student$ git commit -m "My first commit"
   [master (root-commit) 2c1e0af] My first commit
     1 file changed, 1 insertion(+)
     create mode 100644 learning-git.js
   Students-Computer:homework student$ git log
   commit 2c1e0af9467217d76c7e3c48bcf9389ceaa4714b
   Author: Student <lc101.student@email.com>
   Date:  Wed Apr 24 14:44:59 2019 -0500

      My first commit

To break down what happens in a commit even further:

When using ``git status``, the output shows two categories: modified tracked files and modified untracked files.
Modified tracked means that the file exists in the Git repository already, but is different than the version in the repository.
Modified untracked means that it is a new file that is not currently in the repository.

``git add`` adds files to the commit, but it does not commit those files.
By using ``git add .``, all the modified files were added to the commit.
If a programmer only wants to add one modified file, they can do so.

``git commit`` actually commits the files that were added to the repository.
By adding ``-m "My first commit"``, a comment was added to the commit.
This is helpful for looking through the log and seeing detailed comments of the changes made in each commit.

``git log`` shows the author of the commit, the date made, the comment, and a 40-character hash.
This hash or value is a key for Git to refer to the version.
Programmers use these hashes to reference specific commits, or snapshots, in the repository's history.

Check Your Understanding
------------------------

.. admonition:: Question

   What git command is NOT a part of the commit process?

   #. ``git add``
   #. ``git log``
   #. ``git status``
   #. ``git push``
