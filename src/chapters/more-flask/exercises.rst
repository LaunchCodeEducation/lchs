Exercises: Logic Templates
==========================

In this set of exercises, you will add some logic to a Jinja2 template.

Setup
-----

#. Open a new window in Visual Studio Code.
#. Use the *File* menu to open your ``local_practice`` directory.
#. In your browser, navigate to this GitHub repository [INSERT LINK]. Click
   the green *Clone* button and copy the URL.
#. In the terminal, enter the ``git clone repo_address`` command. Be sure to
   replace ``repo_address`` with the URL you copied in step 2.

[INSERT screenshot of the file tree here.]

Shouldn't need to modify the logic in ``main.py``...

Part A: Extend from ``base.html``
---------------------------------

Extend base template into ``grid.html``...

Part B: Add a Loop
------------------

Launch main.py and refresh a few times...

Note that the direction choices in the form are always LRUD. These need to
change depending on which box is the current location...

Describe the ``choices`` dictionary...

In the grid.html template, add a loop:

#. Iterate by key/value pairs.
#. Key = label text for the radio button.
#. Value = index for the destination box.

Change ``GET`` to ``POST``...

Part C: Add a Conditional
-------------------------

Note how the path record changes after each direction choice is made...

We want to display a different 
