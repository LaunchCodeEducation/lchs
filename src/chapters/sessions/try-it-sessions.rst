Try It! Flask Sessions
======================

Let's build a simple Flask application that uses sessions to track a list of
items. It doesn't matter what the list is (movies, groceries, places to visit,
etc.). The key is to practice saving and accessing persistent data.

.. admonition:: Note

   For our program to work properly, cookies must be enabled in your browser.

Clone the Repository
--------------------

The starter code for this demo is saved on GitHub. Use `this link <https://github.com/LaunchCodeEducation/LCHS_session_try_it>`__
to navigate to the repository, then follow these setup steps:

#. On the repository page, click the green *Code* button and copy the URL.

   .. figure:: figures/clone-session-repo.png
      :alt: The clone dialog box with copy button highlighted.

#. Launch Visual Studio Code. From the *File* menu, open your
   ``local_practice`` directory.
#. In the terminal pane, enter the command:

   .. sourcecode:: bash

      $ git clone repo_URL
   
   Be sure to replace ``repo_URL`` with the web address you copied in step 1.
#. From the *File* menu, open the ``LCHS_session_try_it`` folder.
#. Create a new virtual environment and install Flask.

   .. sourcecode:: bash

      Mac:
      $ python3 -m venv session-env
      $ . session-env/bin/activate
      (session-env) $ pip3 install Flask

      PC:
      $ py -3 -m venv session-env
      $ . session-env/Scripts/activate
      (session-env) $ pip install Flask

#. Launch the ``main.py`` program and open the webpage in a browser tab.
   Nothing special happens on the page yet. You just need to make sure the
   starter code runs.

   .. figure:: figures/session-try-it-start.png
      :alt: Form page displayed when the Flask app runs the first time.
      :width: 50%
   
      This is what you will see when the starter code runs.

#. Before moving on, be sure to save and commit your work.

Save Session Data
-----------------

In this section, you'll create a new ``session`` object and use it to store a
piece of data.

Right now, all the Flask application does is render the ``index.html`` page.
Opening ``main.py``, we see very little code inside the central ``if/else``
block.

.. admonition:: Example

   The ``index()`` function in ``main.py``:

   .. sourcecode:: python
      :lineno-start: 7

      @app.route('/', methods=['GET', 'POST'])
      def index():
         if request.method == 'POST':
            pass
         else:
            pass
         return render_template('index.html')

   ``pass`` is another example of a placeholder. The keyword fills the space
   where Python expects a block of statements. Here, it allows you to run a
   starter code successfully and fill in different commands later.

Since your program will track a collection of items, start by saving an empty
list to the session.

#. To set a new session cookie, the general syntax is:

   .. sourcecode:: python

      session['key'] = value
   
   Just like a dictionary, ``key`` should be a string data type. However,
   ``value`` can be any Python data type.

#. In ``main.py``, replace the ``pass`` keyword on line 12 with the statement:

   .. sourcecode:: python
      :lineno-start: 12

      session['list_name'] = []

   Be sure to use something more descriptive than ``list_name``. For example,
   ``movies``, ``places_to_visit``, ``groceries``, etc.

#. Save your changes. If ``main.py`` is not currently running, start it again.
#. In its page tab, use the :ref:`browser tools <cookies-vs-sessions>` to
   confirm that a session cookie was set.

Congratulations! You just made the browser store a file on your device. It only
contains an empty list, but you'll soon fix that.

.. admonition:: Note

   Remember, unlike plain cookies, session values can be non-string data types!

Access Session Data
-------------------

OK, you've saved a session to your device. Now you need to be able to access
that data whenever you need it.

To access session data, the general syntax is:

.. sourcecode:: python

   all_session_data = session

   # OR

   specific_session_value = session['key']

When placed to the right of the ``=`` operator, ``session`` returns all of the
key/value pairs stored. We can use ``all_session_data`` just like a Python
dictionary. 

``session['key']`` returns the value assigned to ``key``. Since the ``session``
object can store multiple key/value paris, this is helpful when we want one
specific entry.

Now put this to use:

#. Open ``index.html`` in Visual Studio Code.
#. Just beneath the form code, there is a section to display the contents of
   the list.

   .. sourcecode:: html
      :lineno-start: 21

      <section class="centered">
         <h2>List Items:</h2>
         <p>(Nothing here yet...)</p>
      </section>

#. Replace the ``(Nothing here yet...)`` text with a placeholder:

   .. sourcecode:: html
      :lineno-start: 21

      <section class="centered">
         <h2>List Items:</h2>
         <p>{{session['list_name']}}</p>
      </section>

#. Save, then reload the page. You should see a set of empty list brackets
   appear on the page.

      [screenshot]
#. Return to ``main.py``. Instead of assigning the empty list to ``session``,
   try assigning a list that contains one or more items. Save, then reload the
   page. You should see the items appear on the page.

      [screenshot]

Notice that we did NOT include any variables in the ``render_template``
function. Since the session data is stored on your device, it is accessible by
``main.py`` and ``index.html``.

Change Session Data
-------------------

Lead in to next page...

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
