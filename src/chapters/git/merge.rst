Merging in Git
==============

Let's say we branch off of ``master`` to work on a new feature for our program.
After some work, debugging, and several commits, we finally get the new code
running (yay). Our next step is to git that code into the master branch of our
program.

.. index:: ! merge
   single: git; merge

We do this by **merging** two separate branches. A merge takes the files and
code from one branch and joins them to the files and code in another. A commit
is automatically created and saves the result in the repository. The two
branches become one, with a shared history and Git log.

[IMAGE]

CAPTION: The ``html-code`` branch is merged into ``master``.

How to Merge
------------

To combine two branches, we must check a few things first:

#. Use ``git status`` to check both branches for uncommitted changes. If found,
   save them to the repository with ``git add .`` and ``git commit -m``.
#. Once the line ``nothing to commit, working tree clean`` appears in the
   ``status`` output for both branches, they are ready to merge.
#. Use ``git checkout`` to switch to the branch that will *receive* the other
   one. For example, if we want to merge ``html-code`` into ``master``, then we
   need to switch into ``master``.

After completing these checks, the terminal syntax for a merge is:

.. sourcecode:: bash

   git merge branch-name

This merges ``branch-name`` into the current one.

.. admonition:: Example

   Use the figure at the top of this page as a model. We want to merge the
   ``html-code`` branch into ``master``.
   
   After we finish the ``git status`` checks, the terminal output would look
   something like this:

   ::

      $ git branch
       * html-code
         master
      $ git checkout master
      Switched to branch 'master'
      $ git merge html-code
      Updating db231f2..5e43d6f
      index.html | 5 ++++-
      1 file changed, 4 insertions(+), 1 deletion(-)
   
   The output after the ``git merge`` command will vary depending on the
   branches involved and how many changes need to be combined.

Try It!
-------

Lorem ipsum...

Merge Conflicts
---------------

Lorem ipsum...

Avoiding Conflicts
^^^^^^^^^^^^^^^^^^

Lorem ipsum...

Check Your Understanding
------------------------

Lorem ipsum...
