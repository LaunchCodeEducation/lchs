Try It! Flask Sessions
======================

Let's build a simple Flask application that uses sessions to track a list of
items. It doesn't matter what the list is (movies, groceries, places to visit,
etc.). The key is to practice saving and accessing persistent data.

.. admonition:: Note

   For our program to work properly, cookies must be enabled in your browser.

Clone the Repository
--------------------

The starter code for this demo is saved on GitHub. Use the link to navigate to
the repository, then follow these setup steps:

.. todo:: Insert GitHub link (sessions Try It! starter code).

#. On the repository page, click the green *Clone* button and copy the URL.

   .. todo:: Insert GitHub repo screenshot (sessions Try It).

#. Launch Visual Studio Code. From the *File* menu, open your
   ``local_practice`` directory.
#. In the terminal pane, enter the command:

   .. sourcecode:: bash

      $ git clone repo_URL
   
   Be sure to replace ``repo_URL`` with the web address you copied in step 1.
#. From the *File* menu, open the ``LCHS_session_try_it`` folder.
#. Return to the terminal and initialize the project as a Git repository.

   .. sourcecode:: bash

      $ git init
#. Create a new virtual environment and install Flask.

   .. sourcecode:: bash

      Mac:
      $ python3 -m venv session-env
      $ . session-env/bin/activate
      (session-env)$ pip3 install Flask

      PC:
      $ py -3 -m venv session-env
      $ . session-env/Scripts/activate
      (session-env)$ pip install Flask

#. Launch the ``main.py`` program and open the webpage in a browser tab.
   Nothing special happens on the page yet. You just need to make sure the
   program runs.

   .. todo:: Screenshot of working session demo app (initial state).

#. Before moving on, be sure to save and commit your work.

Save Session Data
-----------------

Lorem ipsum...

Simple session...

Note that sessions can store non-string data types!

Try It working example...

Access Session Data
-------------------

Lorem ipsum...

Change Session Data
-------------------

Lorem ipsum...

Clear Session Data
------------------

Lorem ipsum...

Demo Ideas/Notes
----------------

#. Text form to add new items.
#. Save list to session object. Use Jinja2 conditional and loop to display the
   list elements on the webpage.
#. After POST, save new item to var, pass it to template, display in message.
   "You just added ____ to the list."
#. Append new item to session list.
#. Checkbox form to remove items. Feedback message?
#. Show that list methods (e.g. pop() and sort()) work with
   session['list_name']?
#. Bonus task: Run secondary program. This one presents a row of numerical
   buttons. Clicking these builds a string. Include a delete key to back up one
   space. This program is just for exploration, not a step-by-step walkthrough.

Check Your Understanding
------------------------

Lorem ipsum...
