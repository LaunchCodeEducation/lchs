Exercises: Flask Sessions
=========================

In these exercises you will build a Flask app that uses sessions to run a
number guessing game.

Part A: Clone the Repository
----------------------------

To save you some time, clone the starter code from this GitHub repository.

.. todo:: Add GitHub repo link (sessions exercises)

#. Follow the same steps you used :ref:`earlier in this chapter <clone-venv-reminder>`
   to download the project files, create a new virtual environment, install
   Flask, and commit your changes.

   .. admonition:: Note

      In the :ref:`.gitignore file <create-gitignore>`. Be sure to use the
      name of your new virtual environment in line 1.

#. When ready, the project file tree should look like this:

   .. todo:: Add a screenshot of the sessions exercises filetree.

#. Launch ``main.py``, and open the Flask app in a new browser tab.

Part B: Set the Numbers
-----------------------

Lorem ipsum...

Students choose the start and end value for the guessing range, then randomly
select an integer as the value to guess.

Save start, end, and guess to the session...

Update ``index.html`` to display start and end values from the session...

Part C: Check User Guesses
--------------------------

Lorem ipsum...

Request data from form. Validate it to make sure it's an integer and within the
proper range. Display an error message for invalid entries.  Note double
checking (client and server side).

Compare guess to magic number. Create feedback message. Update guessing range
values. Render form again.

If correct, change form button to Play Again?

Part D: Optional Updates
------------------------

Lorem ipsum...

Randomly select start and end values?

Add a New Number button to form?

Add a guess counter to report the user's score.

Update number guess to rock-paper-scissors?
