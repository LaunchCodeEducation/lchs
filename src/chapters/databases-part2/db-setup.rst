Database Setup
==============

The Minesweeper game will use a combination of session cookies and database
operations to store important information. Let's begin by getting the database
file ready.

Start With an Outline
---------------------

Before we write any code, we need to think about what data the game needs in
order to work. In particular, we want to identify the information to save in
the game's database. There are LOTS of possibilities! However, for our basic
game, we want to start small. We can always refine the database structure
later!

Consider the data that needs to *persist*. For example, if a user leaves the
game in the middle of play and comes back later, what needs to go into the
database to keep a record of their progress?

For starters, our database should save:

#. Information about each mine hidden on the board. This includes a primary key
   value as well as a location (row letter plus column number).
#. Information about each individual cell on the board. This includes a primary
   key, the cell's location, the number of mines in surrounding cells, whether
   the user has clicked the cell, and whether the cell contains a mine.

This outline suggests at 2 tables in the database - one for a list of mines,
and another for the cells on the game board.

``db_setup.py``
---------------

Use the tools in Visual Studio code to create a new Python file at the same
level as ``main.py``. Call the new file ``db_setup.py``. This will be a
separate program, and its only job is to create the database file and add two
tables.

Follow along with the video to build this program.

.. todo:: Insert video tutorial for the Minesweeper database setup.

Create ``mines`` and ``board`` tables...

.. admonition:: Note

   For our basic game, we might not use all of the columns in the tables yet.
   However, they could be useful later, so there's no harm in adding them now.

Video Summary
-------------

Lorem ipsum...

#. Adding the ``DROP TABLE`` commands at the top of the file lets us reset the
   database in case we need a fresh start.
#. Primary key data type must be ``INTEGER`` and not ``INT``. For some reason,
   the latter syntax doesn't work to automatically increment the primary key
   values.
#. ``NOT NULL`` prevents a row from being inserted if the SQL command leaves
   out a value for that column.
#. Use nested loops to create and assign the coordinates for each cell on the
   board.
#. Note the unused X/Y and 0/11 row/column labels. There's reason for this, but
   we won't go into that now. (Link to game logic section).

.. todo:: Insert link to game logic section here (why include X/Y and 0/11 labels).
