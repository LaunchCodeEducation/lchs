Exercises: Flask Intro
======================

In the following exercises, you will create a Flask application that does the
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

#. From the terminal, use ``python hexcode.py`` to launch the application.
#. Open your browser and navigate to ``http://127.0.0.1:5000/hex_form``.
   Unfortunately, the form doesn't look very nice right now. By moving the
   ``.html`` and ``.css`` files into different directories, we broke the link
   between them.

   .. figure:: figures/plain-hex-form.png
      :alt: Hex form with no image or CSS rules applied.
      :width: 60%
   
      Your webpage rendered, but it needs some work.

#. Open the ``hex_form.html`` file in Visual Studio Code. On line 7, update the
   ``href`` attribute. Replace ``style.css`` with the :ref:`url_for <link-stylesheet-flask>`
   function.

   .. sourcecode:: html
      :lineno-start: 7

      <link rel="stylesheet" type="text/css" href="{{url_for('static', filename='style.css')}}">

#. On line 27, do the same thing to update the ``src`` attribute inside the
   ``<img>`` tag. Be sure to change the filename to ``hex_figure.png``.
#. Save your changes. Refresh the webpage to make sure the style rules and
   image are now in place.

   .. figure:: figures/hex-form-midway.png
      :alt: Hex form with CSS rules and image applied.
      :width: 40%
   
      Your form now.

Add Placeholders
^^^^^^^^^^^^^^^^

Notice that the ``input`` elements on lines 23 and 24 use the hard-coded hex
value ``FF0000``. Every time the page loads, the text in the input box will
always show ``FF0000``, and the color box will always be red. 

.. sourcecode:: html
   :lineno-start: 23

   <label>Enter a code: #<input type="text" name="hex" value="FF0000" required/></label><br>
   <input type="color" value="#FF0000" disabled/>

Add :ref:`placeholders <template-placeholders>` to the template to make the
input boxes change when the form is submitted.

#. In lines 23 and 24, replace ``FF0000`` with the ``{{hex}}`` placeholder:

   .. sourcecode:: html
      :lineno-start: 23

      <label>Enter a code: #<input type="text" name="hex" value="{{hex}}" required/></label><br>
      <input type="color" value="#{{hex}}" disabled/>

   Be sure to keep the ``#`` symbol in line 24. 

#. In line 21, replace the ``Feedback will appear here...`` text with a
   different placeholder. Use whatever variable name you want, but remember to
   surround it with double curly braces ``{{}}``.
#. Now open ``hexcode.py``. Add the ``hex`` and your feedback variable, and
   assign values to them. Also, add arguments to the ``render_template()``
   function to pass those values to the template.

   .. sourcecode:: python
      :lineno-start: 6

      @app.route('/hex_form')
      def hex_form():
         hex = "FF0000"
         feedback = ""

         return render_template('hex_form.html', hex=hex, feedback=feedback)

#. Save your changes and make sure the webpage still works.
#. In the Python code, change the value of ``hex`` to ``00FF00``, ``0000FF``, or ``987654``, then
   refresh the page. It should respond differently to each of the values.
#. Test your feedback placeholder by changing its string in the Python code.
#. Once you have the template responding to the data you send to it, save and
   commit your work.

   .. figure:: figures/working-placeholders.png
      :alt: Input fields responding to Python data.
   
      The values assigned in the Python code show up on the webpage.

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
