Project: Improve the User Experience
====================================

Recall the web form we created in :ref:`the last chapter <server-side-validation>`.
As designed, if the user enters invalid data, they won't know about their
mistake until they reach the results page. This flaw in the user interface (UI)
lowers the quality of the user experience (UX).

One common practice for web forms is to keep a user on the original page when
they make a mistake. Also, displaying an error message about what went wrong
gives the user a smooth way to make corrections.

For this project, you will update a fake account signup to improve the
UI/UX. When a user submits invalid information, the following should happen:

#. The form page will reload,
#. All valid entries will remain in their input fields,
#. One or more messages will appear explaining what went wrong,
#. The user can re-enter information and submit again.

When the user successfully fills out the form, they will be sent to a different
webpage.

Setup
-----

The starter code for this project is saved in the same
`GitHub repository <https://github.com/LaunchCodeEducation/LCHS_flask_logic>`__
you used for the exercises. However, the project code is in a separate branch.

#. Open the ``LCHS_flask_logic`` directory in Visual Studio Code. If you
   haven't downloaded it from GitHub yet, return to :ref:`the exercises <more-flask-exercises-setup>`
   and follow the instructions for cloning the project to your device.
#. In the terminal, switch to the ``project-start`` branch:

   .. sourcecode:: bash
   
      $ git checkout project-start

#. Just like you did for :ref:`the chapter exercises <more-flask-exercises-setup>`,
   create and activate a new virtual environment.
#. Install Flask.
#. Save and commit your work.

Run the Application
^^^^^^^^^^^^^^^^^^^

Launch ``main.py`` and open the application in a new tab in your browser.

As designed, the form works. Submitting a valid set of data will lead to a
success page. However, the user interface needs some major fixes.

Recall that part of a UI is the code that makes it work. However, the
appearance of the interface is just as important.

Part A: Clean Up the View
-------------------------

The layout and colors on the page are a bit distracting. Since this is the
signup page for your web application, it is the first thing new users see. If
it gives them a poor UX, then they might decide NOT to join!

Open the ``style.css`` and ``register.html`` files in Visual Studio Code. Make
the following changes by adjusting the CSS style rules, adding ``class``
attributes inside the HTML tags, or adding new HTML code.

#. Remove the yellow background color from the page.
#. Fix the rainbow background in the header. Just because you *can* apply lots
   of color, doesn't mean you *should*.

   .. admonition:: Tip
   
      Note how the black letters in the heading stand out against the lighter
      colors, but get hard to read on top of the darker colors. The opposite
      would be true for a light text color.

      For best results, try to keep a consistent, sharp contrast between the
      text color and the background.

#. Center the ``h2`` and ``form`` elements on the page.
#. Inside the form, left-align the input labels and center the *Submit* button.
#. Make the font size for the labels and input boxes large enough to easily
   read.
#. Style the *Submit* button to make it stand out more.
#. Below the form, display some rules for filling out the input fields:

   a. The username should be 3-8 characters long. It cannot contain spaces.
   b. The password needs to be 8 or more characters long, with no spaces. Also,
      it should contain at least one letter, one number, and one special symbol
      (``%``, ``#``, ``&``, or ``*``).

#. Once you finish updating the appearance of the page, save and commit your
   work.

The form looks better now, and it does work. However, try entering some invalid
information and click *Submit*.

Notice that the form gets erased, and this is a problem. The code behaves
correctly by rejecting invalid entries. However, the user has no way of knowing
this! To them, the form simply didn't work.

To improve their experience, users need to receive some type of feedback
whenever they submit a form. This will be your focus in the remaining sections.

Part B: Keep Valid Data Intact
------------------------------

One good way to improve the UX is to keep any *correct* entries in place and
remove the incorrect ones. This becomes more and more important as the number
of input fields increases.

Open ``main.py`` and take a look inside the ``registration()`` function. The
``inputs`` dictionary organizes data for the form. Each key is the label for
one of the input fields. Each value is a list with strings to assign to the
``type``, ``name``, and ``placeholder`` attributes.

Inside ``register.html``, note how the ``for`` loop fills in the data from
the ``inputs`` dictionary.

.. sourcecode:: html
   :lineno-start: 7

   {% for (label, attributes) in inputs.items() %}
      <label>{{label}}: <input type="{{attributes[0]}}" name="{{attributes[1]}}" placeholder="{{attributes[2]}}" required /></label>
   {% endfor %}

The ``label`` variable is assigned each key from the ``inputs`` dictionary. The
``attributes`` variable is assigned the list for that key. As written, the
``for`` loop assigns the ``type``, ``name``, and ``placeholder`` values for
each input field. Each time the page loads, the fields get cleared.

#. Inside the ``input`` tag, add the ``value="{{attributes[3]}}"`` attribute.
#. Return to ``main.py``. For each list in the ``inputs`` dictionary, add the
   empty string as the fourth element. For example, 

   .. sourcecode:: Python
      :lineno-start: 51

      inputs = {
         # Label: [type, name, placeholder, value]
         'Username': ['text', 'username', '3-8 characters, no spaces', ''],

#. Add MT string and {{attr[3]}} value attribute...
#. Update ``check_username()`` function. If correct, replace MT string with the
   user's entry. If incorrect, retain the MT string...
#. Repeat for ``check_password()`` and ``check_confirm()``...

Display Error Messages
----------------------

Add another MT string to the end of the ``inputs`` list...

Walkthrough how to add error message for check_username() function...

Repeat for other validation functions...

Redirect on Success
-------------------

``render`` vs. ``return redirect``...

What's to stop users from just entering the results page URL in the address
bar? Nothing!

Add GET/POST check. Redirect on GET (to prevent users from just entering the
URL in the address bar). We'll learn a more secure way to do this later in the
course. This is a crude way of adding security, and it is far from perfect. We
really need a way of checking if the user is logged in *before the page loads*.

Bonus Mission
-------------

Lorem ipsum...

Message flashing: https://flask.palletsprojects.com/en/1.1.x/patterns/flashing/#message-flashing-pattern
