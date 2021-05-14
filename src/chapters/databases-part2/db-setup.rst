Database Setup
==============

Starts with pen and paper! Think about the data the game needs in order to
work.

#. Mine locations on the grid (in the form of row letter and column number).
#. Table for cell info (coords, num surrounding mines, guessed, mine_id).
#. Each row in each table gets a primary key.

Create ``mines`` and ``map`` tables...

Discuss logic behind table columns. We're putting in some extras that we might
use later.

Will use a combination of session cookies and DB entries to run the game...

Video walkthrough...
