.. _flask-game-repo:

Assignment #6: Remote Repository Setup
======================================

In your earlier work, you cloned repositories from GitHub, pushed and pulled
content from the site, and collaborated with a partner on a
:ref:`shared repo <communication-log>`. However, you often performed each these
actions separately from the others.

For this assignment, you will start a project from scratch. Besides making a
cool web application, you will also refine all of your version control skills!

The sections below walk you through the setup for your project. After your
local and remote repositories are linked and ready to go,
:ref:`return to the main Assignment 6 page <flask-game>`.

Create a New Local Repository
-----------------------------

Your first step is to create a *local* project directory. This stores a copy of
your project code on your personal device.

#. Launch Visual Studio Code and use the *File* menu to open your
   ``local_practice`` folder.
#. In the file tree, create a new directory for your game project. Be sure to
   give the folder a descriptive name! Also, make sure the new folder is NOT
   buried inside of a different project.
#. From the *File* menu, open your game folder. In the terminal, run
   ``git init`` to initialize the directory for version control.
#. Use the tools in VS Code to create a file tree that looks like this:

   .. figure:: figures/flask-game-start-tree.png
      :alt: Starting file tree showing static/style.css, templates/index.html, and main.py.

      The file tree contains two folders and three files.

   You don't need any code in ``main.py``, ``index.html``, or ``style.css``
   yet.

#. Use the terminal to create a new virtual environment for your project. Also,
   install Flask. If you need a reminder for how to do this, review the
   guidelines in the :ref:`Cookies & Sessions chapter <clone-venv-reminder>`.
#. Add a ``.gitignore`` file and paste in the :ref:`usual code <create-gitignore>`.
   Be sure to put the name of your project's virtual environment in line 1.
#. Properly done, your file tree should now look something like this:

   .. figure:: figures/flask-game-setup-done.png
      :alt: Project file tree after installing Flask.

      Your local file tree after installing Flask and adding ``.gitignore``.
      
#. Run through the usual ``git status/add/commit`` process to save your
   progress.
#. Finally, use ``git branch`` to check the name of your default branch.

   .. sourcecode:: bash

      $ git branch
      * main

   If the default branch is NOT called ``main``, change it with the command

   .. sourcecode:: bash

      $ git branch -m old_branch_name main

Link to a Remote Repository
---------------------------

The next step is to open an empty repository on GitHub. This will eventually
hold the *remote* copy of your project code.

#. Open your web browser and login to your `GitHub account <https://github.com>`__.
#. On your home screen, click the *New Repository* button.

   .. figure:: figures/new-GH-repo.png
      :alt: Showing the New repository button on the GitHub home screen.

      It's friendly and green. Click the button!

#. This opens up a page where you must make a few choices. First, fill in
   ``Repository Name`` with the SAME NAME as your local game directory. Also,
   give a short description of your project.

   .. figure:: figures/name-GH-repo.png
      :alt: Filling in the name and description for the new repository.

      If your repo name is already taken, you'll have to think of another!

#. Next, select the *Public* option for your repo, and leave the three
   checkboxes empty. Click *Create repository*.

   .. figure:: figures/GH-repo-options.png
      :alt: Select the public repo option.
      :width: 50%

#. The next screen seems very detailed, but it's almost automatic. Copy the
   commands for *pushing an existing repository* and paste them into the
   terminal panel in VS Code. This will *push* the local repo you created
   earlier to your GitHub account.

   You may be asked to enter your GitHub username and/or password to complete
   the action.

   .. figure:: figures/push-local-repo.png
      :alt: Copy the third set of terminal instructions.
      :width: 80%

Good! Your local game directory is now linked to the remote version. You should
be able to see the same files and folders online and in VS Code.

   [Insert GitHub project screenshot]

Add Teammate(s) to Project
--------------------------

Finally, you need to grant your partner(s) permission to make changes to the
remote repository.

In GitHub: Grant edit access to collaborator(s). (Reference Communication
Log assignment).

Ready to Go!
------------

Whew! This process gets easier with practice, and you now have a little more
experience under your belt.

Ready to build your game? :ref:`Return to Assignment 6 <flask-game>`.
