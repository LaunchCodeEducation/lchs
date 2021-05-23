Game Page Logic
===============

Our home page is ready, the database functions operate, and we have access to
ready-made functions in ``game_logic.py``. After we add one final bit of code,
we can finally play our Minesweeper game!

The ``play()`` Function
-----------------------

Open the ``main.py`` file in Visual Studio Code, then code along with the
video:

.. todo:: Insert tutorial video for coding the ``play()`` function.

Video Summary
-------------

Add code to ``main.py`` to deal with:

#. Import functions from ``game_logic.py`` file.
#. Page title string (update with number of mines remaining).
#. Collect cell selection from game form. Validate on server side.
#. Identify if *Flag Mine* was checked.
#. Call the ``check_guess()`` function.
#. Redirect back to home page if ``num_mines`` not set or if an invalid input
   is sent as the guess.

Test the Game!
--------------

Lorem ipsum...

As you play, you will find a few glitches or rough patches. This is expected,
and it's the whole point of testing! Keep a record of the flaws you find, and
note how serious each one is. Errors that crash the application or impact the
gameplay should be addressed before minor annoyances.
