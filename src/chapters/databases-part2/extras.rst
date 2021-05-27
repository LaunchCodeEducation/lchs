Next Steps
==========

Besides squashing bugs, feel free to make changes and experiment with new
features. This page describes several options, but these are only a few of the
directions you can go.

Appearance Options
------------------

#. The styling for the home and game page is pretty minimal. Change the look
   of the website by updating the rules inside the ``style.css`` file.
   Alternatively, import the `Bootstrap <https://getbootstrap.com/docs/5.0/getting-started/introduction/>`__
   library and play around with different ``class`` values.
#. Display instructions for how to play Minesweeper.
#. Automatically resize the table to fit different screens. Scrolling is
   distracting for this type of game! To test resizing behavior, click and drag
   the bottom corer of your browser window. You want the table to grow and
   shrink to keep all the rows and columns in view.
      
   .. figure:: figures/responsive-board.gif
      :alt: The game table resizes to fit the window.
      :width: 70%
   
      Having to scroll to play Minesweeper provides a poor UX. The table should
      resize to fit in the available space.

Gameplay Options
----------------

#. Add a timer.
#. Different game board sizes.
#. Adding more server-side validation for the Main Menu form. Currently, there
   is no check for numbers outside of the 5 - 25 mine range.
#. Clicking the *Back* button causes problems.
#. Entering the URL for the game board *before* visiting the home page throws
   an error. Smooth over this rough patch by checking if ``num_mines`` is in
   the session.

Database Options
----------------

#. Save Game feature. We have all of that session data, which can be loaded
   into a different table in the database. For example, we might want to save a
   user's name and progress, just in case they need to leave the game and come
   back later.
#. Save win/loss data. Preserve initials and fastest times.

   [Screenshot of 80's arcade high score list.]
