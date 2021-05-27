Next Steps
==========

Possible next steps for the game...

#. Save Game feature. We have all of that session data, which can be loaded
   into a different table in the database.
#. Instructions on Home and/or Game page.
#. Resizing the table to fit different screens. Scrolling is distracting for
   this type of game!
#. Add a timer. Preserve names and fastest times.
#. Different game board sizes.
#. Clicking the *Back* button causes problems.
#. Adding more server-side validation for the Main Menu form. Currently, there
   is no check for numbers outside of the 5 - 25 mine range.
#. Other...

For example, we
might want to save a user's name and progress, just in case they need to leave
the game and come back later.

if 'num_mines' not in session or session['num_mines'] <= 0:
