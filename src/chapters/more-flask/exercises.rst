Exercises: Logic In Templates
=============================

In this set of exercises, you will add some logic to a Jinja2 template. You
will begin by cloning some starter code from a GitHub repository. This will
include a ``main.py`` program, but you should not need to modify the Python
code to complete any of the tasks.

However, after you finish the exercises, feel free to explore ``main.py`` to
figure out what its doing!

Setup
-----

#. Open a new window in Visual Studio Code.
#. Use the *File* menu to open your ``local_practice`` directory.
#. In your browser, navigate to this GitHub repository [INSERT LINK]. Click
   the green *Clone* button and copy the URL.

   [INSERT SCREENSHOT HERE]

#. In the terminal, enter the command ``git clone repo_address``. Be sure to
   replace ``repo_address`` with the URL you copied in step 3.
#. Return to the *File* menu and open the ``LCHS_flask_logic`` folder you just
   cloned.
#. Open the terminal panel and create a new virtual environment for the
   project, then activate it. You can name your virtual environment whatever
   you want, but the example below uses ``flask-env``.

   .. sourcecode:: bash

      Mac:
      $ python3 -m venv flask-env
      $ . flask-env/bin/activate

      Windows:
      $ py -3 -m venv flask-env
      $ . flask-env/Scripts/activate

#. Finally, install the Flask module.

   ::

      (flask-env) $ pip install flask

Properly done, you should wind up with this file tree:

.. figure:: figures/exercise-filetree.png
   :alt: File tree for the exercise starter code.

   The file tree required for the start of the exercises.

Part A: Extend from ``base.html``
---------------------------------

Open the ``main.py`` file in VS Code and examine the ``show_grid()`` function.
Notice that ``render_template()`` points to the ``grid.html`` template.

Let's run the web application and see what this template looks like:

#. Make sure ``flask-env`` is active, then launch ``main.py``.
#. Open the web application in the browser. The webpage looks pretty bad right
   now:

   .. figure:: figures/exercises-start.png
      :alt: Disorganized webpage produced by the starter code.
      :width: 60%

#. Open ``grid.html`` in VS Code. The file is missing some boilerplate code
   and a link to the CSS stylesheet. No wonder the page looks so disorganized!
#. The missing code is saved in ``base.html``. Add the three required
   statements to ``grid.html`` to :ref:`extend the base template <extend-base>`.
#. Save your work, then refresh the tab in the browser. The page should look
   much better now.

   .. figure:: figures/exercise-base-applied.png
      :alt: Webpage produced after extending the base template.
      :width: 80%

Before you move on, use ``git status/git add ./git commit -m`` to commit your
work.

Part B: Add a Loop
------------------

For this web application, users submit directions with the form on the right
side of the page. With each entry, the box highlighted in the diagram will
change. Unfortunately, the form does not work yet.

Click the *Refresh* button a few times in the browser. Notice that the
highlighted box in the image changes. However, the direction choices in the
form always remain ``Left``, ``Right``, ``Up``, and ``Down``. Your next task is
to update ``grid.html`` to make these options change based on which box is
active. For example, if box ``0`` is highlighted, the form should only show
``Right`` and ``Down``. For box ``8``, the options should be ``Left`` and
``Up``.

The ``choices`` Dictionary
^^^^^^^^^^^^^^^^^^^^^^^^^^

Describe the ``choices`` dictionary...

Update ``grid.html``
^^^^^^^^^^^^^^^^^^^^

Return to ``grid.html`` in VS Code.

#. Remove three of the four ``label`` elements in the form.
#. In the one that remains, use placeholders for the label text and the
   ``value`` attribute

   .. sourcecode:: html
      :lineno-start: 13

      <label><input type="radio" name="choice" value={{value}} required />{{direction}}</label>

#. Remember the format for the ``choices`` dictionary. Each *key* is a
   direction label for a radio button. The *value* is the number of the target
   box in the image.
#. Add a ``for`` loop that :ref:`iterates over the key/value pairs <jinja2-dictionary-iteration>`
   in the ``choices`` dictionary. The ``label`` element should be the only
   thing inside the body of the loop.
#. Save your work, then reload the page in the browser.
#. Test your work!

   a. Refresh the page several times. Make sure that the options displayed in
      the form are correct for the highlighted box.
   b. Select an option in the form and submit it. Do this several times. As
      long as you didn't change anything in ``main.py``, this should work. If
      an error occurs, check your code in ``grid.html``.
   c. Notice that the ``Path`` element below the image updates each time you
      submit the form.

Before you move on, take a moment to save and commit your work.

Part C: Add a Conditional
-------------------------

Note how the path record changes after each direction choice is made...

We want to display a different 
