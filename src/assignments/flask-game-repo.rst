Assignment #6: Remote Repository
================================

Lorem ipsum...

Part 2: Create a GitHub Repository
----------------------------------

Since you will work on this project from multiple locations, on different
devices, and as part of a team, keeping track of your code is critical.

To help manage this, you will save your project on `GitHub <https://github.com>`__.
Follow the steps below to create a new Git repository, push it up to GitHub,
and give your partner permission to make edits.

New Local Repository
^^^^^^^^^^^^^^^^^^^^

#. Launch Visual Studio Code and use the *File* menu to open your
   ``local_practice`` folder.
#. Create a new directory for your game project. Be sure to give the folder a
   descriptive name!
#. From the *File* menu, open the new folder. In the terminal, run ``git init``
   to initialize the directory for version control.
#. Use the tools in VS Code to create a file tree that looks like this:

   .. figure:: figures/flask-game-start-tree.png
      :alt: Starting file tree showing static/style.css, templates/index.html, and main.py.

   You don't need any code in ``main.py``, ``index.html``, or ``style.css``
   yet.

#. Use the terminal to create a new virtual environment for your project. Also,
   install Flask. If you need a reminder how to do this, review the guidelines
   from the :ref:`Cookies & Sessions chapter <clone-venv-reminder>`.
#. Add a ``.gitignore`` file and paste in the :ref:`usual code <create-gitignore>`.
   Be sure to use the name of your project's virtual environment in line 1.
#. Properly done, your file tree should now look something like this:

   .. figure:: figures/flask-game-setup-done.png
      :alt: Project file tree after installing Flask.

      Your local file tree after adding Flask and ``.gitignore``.
      
#. Run through the usual ``git status/add/commit`` process to save your
   progress.

Remote Repository
^^^^^^^^^^^^^^^^^

#. In GitHub: New repo button, ignore README option, copy/paste push local
   repo git commands.  VS Code might prompt you for your login credentials.
#. In GitHub: Grant edit access to collaborator(s). (Reference Communication
   Log assignment).
