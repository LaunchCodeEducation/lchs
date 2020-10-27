Branching Out
=============

What if we want to experiment with a new feature, and we know that we will need
to make several commits before its done? Similarly, what if two students want
to work on different parts of a project at the same time?

For example, one student could work on some HTML code while their partner
completes the CSS. They can both work during class to save themselves some
time. However, their commits won't follow the same path. Each person will have
their own version of the Git history for the same project. As we saw on the
previous page, this is not a good idea.

Unless...

.. todo:: Insert initial Git branch image here.

CAPTION: "Branches to the rescue."

.. index:: ! branch

.. index::
   single: git; branch

Branching in Git
----------------

Git allows us to store different versions of our code as we create a project.
It also lets us split project development into different paths.

A Git **branch** is a separate version of the same master code. Like a branch
on a tree, a branch in Git shares the same trunk as other limbs. However, each
branch is distinct from all of the others.

With branches, the two students can work on *separate* versions of the same
project. They won't need to worry about messing up each other's work every time
they want to make a new commit. They will share the same base code, and they
will update their own parts of it.

Branches let programmers start, update, store, and test new features for their
code without disrupting the main flow of the Git history.

On Branch Master
----------------

In the :ref:`previous section <check-git-status>`, we used ``git status`` to
check the state of the ``git_practice`` repository. The first line in the
output was ``On branch master``.

When we run ``git init`` to start a new repo, part of the process creates a
single, default branch called ``master``. Many programmers consider this Like
the trunk of a tree. They use master to store and track the main, working
part of their code. They use other branches to experiment with new features and
split up work between partners.

.. admonition:: Tip

   Working on a new part for your code? Do that in a different branch! That
   way, your commits won't interfere with the working copy of your program.

.. todo:: Insert second Git branch image here (master with side branches and commits.

To see a list of all the active branches in a project, enter ``git branch`` in
the terminal.

.. admonition:: Try It!

   Open VS Code and navigate into the ``git_practice`` directory.

   .. sourcecode:: bash
      :linenos:

      $ git branch
      * master

For our ``git_practice`` repo, we only have one branch so far. Let's add
another.

Create a New Branch
-------------------

To create a new branch, the general terminal syntax is:

.. sourcecode:: bash

   git checkout -b branch-name

``-b`` creates a new branch called ``branch-name``, and ``checkout`` switches
us into that branch.

.. admonition:: Try It!

   #. In VS Code, enter the following commands in the terminal pane. Feel free
      to think up your own name for the new branch, but it cannot contain any
      spaces.

      .. sourcecode:: bash

         $ git checkout -b hello-branch
         Switched to a new branch 'hello-branch'
         $ git branch
         * hello-branch
           master
      
      Notice that in the list of branch names, the one we are currently on is
      highlighted with a ``*``. The name might also appear in a different
      color.
   #. Enter ``git log`` into the terminal. Notice that the repo history is the
      same as before. When we created ``hello-branch``, we split it off of
      master and made a copy of all its code.
   #. Add a new file to ``git_practice`` called ``greeting.py``. Inside this
      Python file, add statements to print a simple, polite greeting.
   #. Save and commit your changes. The terminal output will look something
      like:

      ::

         $ git status
         On branch hello-branch
         Untracked files:

            greeting.py

         $ git add .
         $ git commit -m "Added greeting.py file to the project."
         [hello-branch d99e424] Added greeting.py file to the project.
         1 file changed, 1 insertion (+)
         create mode 100644 greeting.py

   #. Enter ``git log`` again and notice that there is a new entry at the top
      of the output.

OK. We created a new branch, added a file, put in some code, and committed all
of those changes to the repository. What's going on back in ``master``?

Switching Between Branches
--------------------------

Now that ``git_practice`` has two different branches, we can switch between
them with the syntax:

.. sourcecode:: bash

   git checkout branch-name

Enter ``git checkout master`` into the terminal. Pay close attention to the
file tree in VS Code and the ``greeting.py`` tab in the editor.

.. todo:: Insert GIF of switching between branches.

Notice that ``greeting.py`` disappears from the file tree! Also, the note
``(deleted)`` appears in its editor tab.

Fear not! Our work hasn't gone away. Enter ``git checkout hello-branch`` in the
terminal to see the file and its code reappear.

The ``checkout`` command switches between branches. When we first made
``hello-branch``, it was identical to master. Once me committed some changes,
however, the two branches became different. By flipping back and forth between
them, we call up different versions of our project.

.. admonition:: Try It!

   #. Create a new branch off of master.
   #. Add some comments to ``num_guess.py``.
   #. Save and commit the changes.
   #. Use ``git branch`` to see a list of branches in the repo.
   #. Use ``git checkout`` to switch between the branches. Notice how the file
      tree and code update as you do so.

Check Your Understanding
------------------------

.. admonition:: Question

   What is a reason for creating a branch in Git?

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> To split work between team members.</li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> To try out a new feature before adding it to the main program.</li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> To avoid conflicts in the repo history.</li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, true)"> All of the above.</li>
      </ol>
      <p id="Q1"></p>

.. Answer = d

.. admonition:: Question

   Do you think we can create a branch off of a branch?

   [IMAGE]

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, true)"> Yes.</li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> No.</li>
      </ol>
      <p id="Q2"></p>

.. Answer = a

.. raw:: html

   <script type="text/JavaScript">
      function evaluateMC(id, correct) {
         if (correct) {
            document.getElementById(id).innerHTML = 'Yep!';
            document.getElementById(id).style.color = 'blue';
         } else {
            document.getElementById(id).innerHTML = 'Nope!';
            document.getElementById(id).style.color = 'red';
         }
      }
   </script>
