Game Page Logic
===============

Our home page is ready, the database functions operate, and we have access to
ready-made functions in ``game_logic.py``. After we add one final bit of code,
we can finally play our Minesweeper game!

The ``play()`` Function
-----------------------

The ``play()`` function controls the game page. It renders the ``mines.html``
template, collects and validates data from the form, calls a function to
analyze each guess, and redirects players to the home page as needed.

Open the ``main.py`` file in Visual Studio Code, then code along with each of
the following videos.

Collect and Validate Guesses
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. raw:: html

   <section class="vid_box">
      <iframe class="vid" src="https://www.youtube-nocookie.com/embed/aDLCNfNkS5U" frameborder="1" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
   </section>

Collect Checkbox Data and Call ``check_guess()``
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. raw:: html

   <section class="vid_box">
      <iframe class="vid" src="https://www.youtube-nocookie.com/embed/P_P5l7GQ_9Y" frameborder="1" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
   </section>

Update ``mines.html``
---------------------

The ``check_guess()`` function returns ``True`` each time the user clicks on a
safe cell on the game board. This happens when the cell does NOT contain a
mine, or if the user selects the *Flag Mine* option before clicking on the
cell. ``check_guess()`` returns ``False`` when the player chooses a cell that
contains a mine.

There are 4 possibilities for the cells in the table. Each one is either:

#. **Unselected**: These appear with a gray background and have an active, blue
   button.
#. **Selected and safe**: These appear with a white background and display a
   number showing how many mines are in the surrounding spaces.
#. **Flagged**: These appear with a goldenrod background and have an active,
   blue button.
#. **Mined**: These appear with a red background and an inactive button.
   Clicking a mined cell ends the game and reveals the locations of all
   remaining mines on the board.

The ``play()`` and ``check_guess()`` functions determine the appearance for
each cell on the game board. However, we need to update the code in
``mines.html`` to properly display the results.

Open the ``game_logic.py`` and ``mines.html`` files in Visual Studio Code, then
code along with the following video.

.. todo:: Insert third video for finishing the Minesweeper game.

Video Summary
-------------

#. Collect cell selection from game form. Validate on server side.
#. Identify if *Flag Mine* was checked.
#. Call the ``check_guess()`` function.
#. Redirect back to home page if ``num_mines`` not set or if an invalid input
   is sent as the guess.
#. Add Jinja3 conditionals to check cell conditions. These determine the
   appearance of each cell in the table.

Test the Game!
--------------

Lorem ipsum...

As you play, you will find a few glitches or rough patches. This is expected,
and it's the whole point of testing! Keep a record of the flaws you find, and
note how serious each one is. Errors that crash the application or impact the
gameplay should be addressed before minor annoyances.
