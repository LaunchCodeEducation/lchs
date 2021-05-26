Gameplay Functions Review
=========================

Several ready-made functions in the starter code...

This page describes how each of these functions work. Note that the code shows
ONE way of accomplishing the Minesweeper gameplay tasks. There are many other
ways to achieve the same results. Feel free to create a new branch in your Git
repository and experiment with other ideas. You can try to streamline the
functions, or replace any of them with a different set of statements.

Note this is an optional page for the students! They got the complete code
from GitHub when they cloned the repo.

Some sections might be short enough for text. The more involved functions will
each get their own video walkthrough.

The ``game_logic.py`` Module
----------------------------

Note the imported modules...

Lorem ipsum...

The ``make_columns()`` Function
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Lorem ipsum...

The ``make_rows()`` Function
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Lorem ipsum...

The ``place_mines()`` Function
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Lorem ipsum...

The ``check_guess()`` Function
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Lorem ipsum...

The ``check_guess()`` function returns ``True`` each time the user clicks on a
safe cell on the game board. This happens when the cell does NOT contain a
mine, or if the user selects the *Flag Mine* option before clicking on the
cell. ``check_guess()`` returns ``False`` when the player chooses a cell that
contains a mine.

The ``crud.py`` Module
----------------------

Lorem ipsum...

The ``check_surroundings()`` Function
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Discuss the check_surroundings() function. Note the *nested* loops for the
systematic row and column checks.
