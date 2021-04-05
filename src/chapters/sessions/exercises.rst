Exercises: Flask Sessions
=========================

In these exercises you will build a Flask app that uses sessions to run a
number guessing game.

Part A: Clone the Repository
----------------------------

To save you some time, clone the starter code from this
`GitHub repository <https://github.com/LaunchCodeEducation/LCHS_session_exercises>`__.

#. Follow the same steps you used :ref:`earlier in this chapter <clone-venv-reminder>`
   to download the project files, create a new virtual environment, install
   Flask, and commit your changes.

   .. admonition:: Note

      In the :ref:`.gitignore file <create-gitignore>`. Be sure to put the
      name of your new virtual environment in line 1.

#. When ready, the project file tree should look something like this:

   .. figure:: figures/session-exercises-file-tree.png
      :alt: File structure for the session exercises starter code.

      The name you gave to the virtual environment will appear instead of ``session-env``. 

#. Launch ``main.py``, and open the Flask app in a browser tab. You should see
   a plain looking web form.

   .. figure:: figures/exercises-start.png
      :alt: A web form for entering numerical guesses.
      :width: 80%

      The ``index.html`` page rendered by the starter code.

Part B: Set the Numbers
-----------------------

Your first task is to save three numbers to the ``session`` object: the
``magic_number`` players need to guess, and the starting and ending values for
a guessing range.

#. Open ``main.py`` in Visual Studio Code. Notice that variables for
   ``low_value``, ``high_value``, and ``magic_number`` are already set.

   .. sourcecode:: python
      :lineno-start: 13

      low_value = 1     # Sets the low end of the guessing range.
      high_value = 50   # Sets the high end of the guessing range.
      magic_number = random.randint(low_value, high_value)

   Line 15 randomly selects an integer from within the allowed range and
   assigns it to the ``magic_number`` variable.
#. Refactor line 15 to save the random integer to the ``session`` object.
   Use ``magic_number`` as the key.

   .. sourcecode:: python
      :lineno-start: 15

      session['magic_number'] = random.randint(low_value, high_value)
#. On lines 16 and 17, save the low and high values to the session object.
   Remember to use descriptive key names!

Display the Number Range
^^^^^^^^^^^^^^^^^^^^^^^^

Open the ``index.html`` file. Notice that the label for the input box always
displays the same text, ``Guess a number between 1 and 100``.

#. Replace the ``1`` and ``100`` with placeholders. Inside each set of braces,
   use the session object to access the low and high ends of the guessing
   range.
#. Save the changes, then reload the webpage. Does the label now show a
   different range?
#. Return to ``main.py`` and change the numbers assigned to ``low_value`` and
   ``high_value``. After saving, reload the webpage.
#. When your page correctly displays the numbers saved to the session, stop the
   program and commit your code. You're ready to move on.

.. admonition:: Tip

   Did you change the ``Form title goes here`` text? You weren't given any
   instructions to do so. However, at this point in the class, we shouldn't
   need to tell you how to fix every minor thing!

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
