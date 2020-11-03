.. _git-project:

Project: Git a Remote Repository
================================

In this activity, you are going to create a remote repository and practice
pushing changes to it from your local machine.

Step 1: Create a New Local Repository
-------------------------------------

#. Launch Visual Studio Code and open the terminal panel.
#. Navigate into the ``local_practice`` directory and create a new folder. You
   can name it whatever you want, but you will be reusing code from your
   :ref:`Turtle Races <turtle-races>` project.
#. Use the *File* menu to open the new folder in VS Code. In the terminal, use
   ``pwd`` to confirm that you are in the correct directory.
#. Use ``git init`` to initialize your project as a Git repository.
#. Move your ``turtle_race.py`` file into the directory. You an do this with
   :ref:`terminal commands <terminal_mv>`, or you can drag-and-drop the
   existing file into the folder.
#. Run ``turtle_race.py`` to confirm that it still works. If not, debug your
   program to get it running again.
#. Save and commit the changes.
#. Check the name of your default branch with the ``git branch`` command. If
   necessary, use ``git branch -m`` to change the name of the branch to
   ``main``.

.. admonition:: Note

   If you did not complete the Turtle Races project, no worries. Just add a
   new Python file to the repository. Code a simple ``print`` statement
   inside a loop and run with that.

Step 2: Create a Remote Repository
----------------------------------

#. Login to your `GitHub <https://github.com/>`__ account in a web browser.
   Click on the "+" button to add a new repository.

   .. figure:: figures/project/new-repo-button.png
      :alt: The New Repository link in the dropdown menu at top right on GitHub.

      The *New Repository* link is in the dropdown menu at top right on GitHub.

#. To create a new repository:

   a. Fill in the name and description. 
   b. Uncheck *Initialize this repository with a README* and click
      *Create Repository*.

   .. figure:: figures/project/create-repo.png
      :alt: Creating a new repository in GitHub by filling out the form.
      :width: 80%

      Create a new repository in GitHub

#. On the next screen, click on the *HTTPS* button at the top of the page.
   Next, click the *Copy* button in the *push an existing repository* section.

   .. figure:: figures/project/new-repo-push.png
      :alt: The page you see after creating an empty repository, with several options.
      :width: 80%

      Connecting to a repository in GitHub

#. Go back to your terminal and paste the commands copied from GitHub. These
   should be very similar to:

   ::

      $ git remote add origin https://github.com/username/turtle-races.git
      $ git branch -M main
      $ git push -u origin main

#. GitHub should now have the same files and code as your local project. Look
   around to see what's there. You can see all of your code on GitHub by
   clicking on different file names.

   [IMAGE - First commit of turtle races]

      A repository with one commit in GitHub

#. Your local and remote repositories are now linked. In the terminal, use the
   ``git remote -v`` command to check for the URL of the remote repo.

   ::

      $ git remote -v
      origin  https://github.com/username/turtle-races.git (fetch)
      origin  https://github.com/username/turtle-races.git (push)

Step 3: Push to the Remote Repository
-------------------------------------

Right now, your local and remote repositories match. As you continue working on
your local device, the two repos become different. From time to time, you need
to *push* your local commits up to GitHub to keep the local and remote versions
the same.

#. In VS Code, add a new text file called ``README.txt``. Inside the file,
   add a short description of your Turtle Races project.
#. Save and commit your changes to the local repo.
#. To update the version stored on GitHub, enter the command
   ``git push origin main`` in the terminal. The output includes information
   about what's happening on GitHub. The final lines indicate if the push was
   successful, and they will look something like: 

   ::

      To github.com:username/turtle-races.git
         7d893b9..20df60b  main -> main

#. After making the push, you should see ``README.txt`` added to the GitHub
   repository.

   [IMAGE - GitHub GUI after push.]

Push up a New Branch
^^^^^^^^^^^^^^^^^^^^

Whenever you push changes up to GitHub, the action only affects the current
branch. In the steps above, you updated ``main``.

#. Back in VS Code, use ``git checkout -b`` in the terminal to create a new
   branch called ``readme``.
#. In the new branch, make some changes to the ``README.txt`` file. Save and
   commit those changes.
#. Your local repository contains two branches now, but GitHub only knows about
   one. If we try ``git push origin readme``, we get an error message:

   ::

      $ git push origin readme

      Lorem ipsum...

#. Fortunately, Git gives us instructions for fixing this. Copy and paste the
   suggested command into the terminal.

   ::

      Lorem ipsum...

#. After this push, you see a list of branches in the main project page of the
   repo. Selecting from the list brings up the files and code stored in that
   branch.

   [IMAGE - branch dropdown menu]

In :ref:`Assignment #5 <communication-log>`, you will learn how to perform a
merge in GitHub. For now, we will leave the branches separate.

Step 4: Pull Down Changes From the Remote
-----------------------------------------

If you are working with a team on a project, it is very likely that one of your
partners will push up changes to GitHub. When this happens, you need to *pull*
those changes down to your own device.

To practice this, you will make a change in GitHub and then move those changes
to your local repo.

#. In your GitHub project page, select the ``readme`` branch.
#. Click on the ``README.txt`` file name, then select *Edit*.

   [IMAGE - Open the file editor in GitHub]

#. Add some more text to the file, or change the words already there. Click the
   *Save* button when done.

   [IMAGE - Save edits.]

#. Return to VS Code, and make sure you are in the ``readme`` branch.

   ::

      $ git branch
      * main
      readme
      $ git checkout readme

#. Enter the command ``git pull origin readme``. Just like ``git push``, the
   output tells you what's happening to your local files. The final lines indicate if the push was
   successful, and they will look something like:

   ::

      Output...

   The ``+`` and ``-`` symbols indicate additions or deletions from the listed
   files.

Bonus: Clone Your Repository to Another Machine
-----------------------------------------------

Lorem ipsum...
