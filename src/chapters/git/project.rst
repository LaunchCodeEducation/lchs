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
#. Now you need to update the GitHub repo. Enter the command
   ``git push origin main`` in the terminal. The output will look something
   like:

   ::

      $ git push origin main

Push up a New Branch
^^^^^^^^^^^^^^^^^^^^

Lorem ipsum...

Step 4: Pull Down Changes From the Remote
-----------------------------------------

Lorem ipsum...
