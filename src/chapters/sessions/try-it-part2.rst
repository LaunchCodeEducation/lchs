Try It! Flask Sessions (Part 2)
===============================

Now that we can set and access a Flask session, let's collect entries from the
form and add the items to our list.

.. admonition:: Note

   In the code blocks below, the generic ``list_name`` has been replaced with
   ``groceries``. Feel free to use a different variable name to better describe
   the elements in your own list.

Add Form Entries to List
------------------------

The HTML code for the form is complete. However, there is currently no code in
``main.py`` to handle form submissions. Let's fix that.

Return to ``main.py``, and replace the ``pass`` keyword in line 10 with this
block of 4 statements:

.. sourcecode:: python
   :lineno-start: 7

   @app.route('/', methods=['GET', 'POST'])
   def index():
      if request.method == 'POST':
         new_item = request.form['new_item']
         current_list = session['groceries']
         current_list.append(new_item)
         session['groceries'] = current_list
      else:
         session['groceries'] = []

**Code breakdown**:

#. **Line 10**: Requests the entry submitted from the web form and assigns the
   string to ``new_item``.
#. **Line 11**: Retrieves the ``groceries`` value stored in ``session`` and
   assigns it to ``current_list``.
#. **Line 12**: Appends ``new_item`` to the end of ``current_list``.
#. **Line 13**: Reassigns ``current_list`` to the session.

Since ``groceries`` is already a key in ``session``, line 13 replaces its old
value with the updated list.

Save the changes, then reload the webpage. Try submitting a few new items from
the form. You should see each entry appear on the page after you click the
*Add Item* button.

Avoid Duplicate Entries
^^^^^^^^^^^^^^^^^^^^^^^

As written, the Python code allows users to add the same item to the list
multiple times. While this behavior isn't wrong, it doesn't fit with the
``groceries`` example.

#. Add a conditional to the code to check if ``new_item`` is already present in
   ``current_list``. If so, don't add it again. If not, append it to the list.
#. To prevent issues with case (e.g. ``"Apples"`` vs. ``"apples"``), add a
   string method to the form request on line 10. ``.lower()``, ``.upper()``,
   ``.capitalize()``, and ``.title()`` all work well.
#. Your code will look something like this:

   .. sourcecode:: python
      :lineno-start: 10

      new_item = request.form['new_item'].title()
      current_list = session['groceries']
      if new_item not in current_list:
         current_list.append(new_item)
      session['groceries'] = current_list
#. Save your changes, then test your application.

Fix the Logic Error
^^^^^^^^^^^^^^^^^^^

When the browser sends a ``GET`` request to the Flask server, the ``index()``
function saves an empty list to the ``session``.

.. sourcecode:: python
   
   session['groceries'] = []

While this is fine the first time we visit the page, it doesn't help if we have
existing data.

.. admonition:: Try It!

   In the program tab, click in the address bar and tap *Enter*. This sends a
   ``GET`` request from the browser. Notice that any list items displayed on
   the page disappear!

This isn't ideal behavior. If our list already contains data, we want to keep
those elements after a ``GET`` or ``POST`` request.

Before assigning an empty list to the ``groceries`` key, we need to check to
see if that key already exists in ``session``. If ``groceries`` is NOT part of
the session yet, then we should add it and assign the empty list. If
``groceries`` is currently a key in ``session``, then we keep it as-is.

Update the ``else`` clause in the ``index()`` function as follows:

.. sourcecode:: Python
   :lineno-start: 7

   @app.route('/', methods=['GET', 'POST'])
   def index():
      if request.method == 'POST':
         new_item = request.form['new_item']
         current_list = session['groceries']
         if new_item not in current_list:
            current_list.append(new_item)
         session['groceries'] = current_list
      else:
         if 'groceries' not in session:
            session['groceries'] = []

Lines 16 & 17 take care of the ``groceries`` check. Now when the browser sends
a ``GET`` request, the conditional makes sure the application preserves any
existing data.

.. admonition:: Try It!

   Test your program by adding a few items to the list. Then try:
   
   #. Loading the page from the address bar.
   #. Opening the application in a new tab.
   #. Stopping and restarting ``main.py``.

   In each case, the contents of your list should persist.

Delete Session Data
-------------------

Lorem ipsum...

Final Touches
-------------

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
