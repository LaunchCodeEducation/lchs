Exercises: Flask Intro
======================

In the following exercises, you will set up a Flask application that does the
following:

#. Uses a form to collect a :ref:`hex code <turtle-color>` from the user.
#. Validates the submitted code.
#. Returns feedback to the user.
#. Displays the color produced by the hex code.

Part A: Setup
-------------

The starter code for this project is stored in a GitHub repository. You will
need to :ref:`clone this repo <clone-repo>` to your device.

#. Open your ``flask_projects`` folder in Visual Studio Code. Enter ``pwd`` in
   the terminal to verify your path.

   ::

      $ pwd
      /Users/username/Desktop/local_practice/flask_projects

#. Download the stater code into this directory. In the terminal, enter the
   command:

   ::

      $ git clone https://github.com/LaunchCodeEducation/lchs_flask_intro.git

#. Use *File --> Open* to open the ``lchs_flask_intro`` folder. You should see
   five files in the left panel.

   .. figure:: figures/exercises-start.png
      :alt: File tree showing 5 items.

      Your starter code is ready!

Install Flask
^^^^^^^^^^^^^

Use the terminal to :ref:`create a virtual environment <venv-flask>`, activate
it, and install Flask to your project.

::

   Mac Users:
   $ python3 -m venv exercises-env
   $ . exercises-env/bin/activate
   (exercises-env) $ pip install Flask

   Windows Users:
   $ py -3 -m venv exercises-env
   $ . exercises-env/Scripts/activate
   (exercises-env) $ pip install Flask

Add Directories
^^^^^^^^^^^^^^^

Remember that Flask requires you to store your templates and supporting files
in specific places inside your project.

#. Use the buttons in the file explorer to create the ``static`` and
   ``templates`` directories.
#. Drag the HTML file into ``templates``. Move the image and CSS files into
   ``static``.
#. Your file tree should now look like this:

   .. figure:: figures/flask-tree-start.png
      :alt: The project file tree after adding Flask and two directories. 

#. Before moving on, make sure to save and commit your work.

Part B: Render the Form
-----------------------

Launch the program, and navigate to the proper URL.

Show desired and actual appearance. (No CSS yet!)

Link to stylesheet and image with ``url_for``.

Add placeholder for feedback.

Add placeholder for ``value`` attributes.

Assign hex and feedback values, and pass them to the template.

Part C: Collect User Input
--------------------------

Add ``action`` and ``method`` attributes.

Add GET and POST methods to route decoration.

Show request.form == "POST" in a conditional.

Submit several valid codes and note how the page changes.

Part D: Validate the Input
--------------------------

Add length check.

Add character check.
