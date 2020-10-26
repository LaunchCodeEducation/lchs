Navigating Commits
==================

After adding a series of commits to a Git repository, we can navigate through
them. If necessary, we can also restore an older version of our code.

Let's add one more commit to the ``git_practice`` repo. Then we will learn how
to move through its history.

Commit to ``num_guess.py`` Again
--------------------------------

#. Add some more statements to your code in ``num_guess.py``. You don't need
   anything fancy. Any simple, working program that is different from what you
   committed before will work.

   Feel free to use the LCHS code `here <https://repl.it/@launchcode/Simple-number-guessing-game#main.py>`__.
#. Use ``git status``, ``git add .``, and ``git commit -m`` to save a new
   commit to the repository.

You should now have at least three total commits in the repo.

Commit Log
----------

In the terminal, enter the command ``git log`` and examine the output. The
command displays a record of every commit in the repository. The top entry is
the most recent.

.. admonition:: Example

   The log for the three entries in the ``git_practice`` repo will look
   something like this:

   ::

      $ git log
      commit 39ab2d77c7813c67958e996961ddbca7a32b6762 (HEAD -> master)
      Author: I. M. Great <student@schoolname.edu>
      Date:   Mon Oct 26 15:46:41 2020 -0500

         Pasted in code from the LCHS number guessing repl.

      commit 479b8b3d84d485cff213015dfcf45b04ef7ea783
      Author: I. M. Great <student@schoolname.edu>
      Date:   Mon Oct 26 14:35:00 2020 -0500

         Added random number selection code.

      commit e14be18ae18e47084fca7d97f25474762b7e8a40
      Author: I. M. Great <student@schoolname.edu>
      Date:   Mon Oct 26 14:23:17 2020 -0500

         My first commit.

.. admonition:: Tip

   If the output reaches the bottom of the terminal pane before finishing, tap
   the space bar to display the next section of text. To stop the output and
   return to the command prompt, tap ``q``.

Each entry in the log contains four items:

#. ``commit`` shows a 40-character long code. This code provides a key that Git
   uses to organize the commits in the repository.
#. ``Author`` indicates who made the commit. This becomes important when
   multiple coders work on the same project. For now, this line shows the name
   used to login to the computer.
#. ``Date`` indicates the day and time the commit was made.
#. The indented line shows the comment saved with the commit. The more details
   we include in each comment, the easier it is to look through the log and
   know what changes were made between saves.

Switching Between Commits
-------------------------

Lorem ipsum...

How to switch...

Note how the latest code "disappears" when switching to an earlier commit...

Restoring earlier commit...

Advancing code, make a mistake, and need to return to the most recent commit...
