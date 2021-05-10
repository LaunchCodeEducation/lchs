.. _movie-sql-part-2:

Project: Movie SQLs (Part 2)
============================

Now that each of your CRUD functions creates a ``sql_query`` string, the next
step is to perform those actions! On this page, you will add a new function to
your Python code. Its job is to execute any query string it receives.

Define the ``execute_query`` Function
-------------------------------------

#. BEFORE the ``index()`` function, paste in this starter code for the
   ``execute_query()`` function:

   .. sourcecode:: Python
      :lineno-start: 8

      def execute_query(query_string):
         db = sqlite3.connect('project.db')
         cursor = db.cursor()
         if "select" in query_string.lower():
            pass
         else:
            pass
         db.close()
         return

      @app.route('/', methods=['GET', 'POST'])
         def index():

   a. Line 8 defines the function with a single parameter. ``query_string``
      receives the SQL queries created by the other functions.
   b. Lines 9 and 10 open a connection to the database and initialize the
      ``db`` and ``cursor`` objects.
   c. Line 15 closes the connection to the database after each SQL query.
   d. Lines 11 - 14 will contain the code to run the SQL queries.
#. Note the condition in line 11. If the SQL query calls for a SELECT
   operation, the function will return a list of results from the database.
   Update the code to assign those results to a variable, then return them.

   .. sourcecode:: Python
      :lineno-start: 8

      def execute_query(query_string):
         db = sqlite3.connect('project.db')
         cursor = db.cursor()
         if "select" in query_string.lower():
            results = list(cursor.execute(query_string)) # Create a list of data from project.db.
         else:
            pass
         db.close()
         return results    # Return the results of the SQL query.
#. The INSERT, UPDATE, and DELETE queries all follow the same the pattern of
   execution. Add the following code to the ``else`` clause:

   .. sourcecode:: Python
      :lineno-start: 8

      def execute_query(query_string):
         db = sqlite3.connect('project.db')
         cursor = db.cursor()
         if 'select' in query_string.lower():
            results = list(cursor.execute(query_string))
         else:
            cursor.execute(query_string)  # Execute the query.
            db.commit()                   # Commit the changes to the database.
            results = 'success'           # Assign a value to 'results'.
         db.close()
         return results

There are still some holes in the ``execute_query()`` code, but this will get
you started. For the next step, you will run some test queries.

.. admonition:: Note

   The code for displaying the query results is already part of ``base.html``.
   Feel free to explore the Jinja2 logic in the template to see how it uses
   the data from ``render_template()`` and the session cookie.

Don't Expect Perfect Syntax
^^^^^^^^^^^^^^^^^^^^^^^^^^^

Launch ``main.py``, then run these two test cases:

#. From the home page, choose ``SELECT`` and ``movies``. Enter ``*`` in the
   first box and leave the WHERE box empty.

   If your ``execute_query()`` function works, you will see a table of data
   appear below the form.
#. Submit the form again, but this time use a column name that does NOT appear
   in the ``movies`` table. How does your program respond?

Yikes! Hopefully, you saw your program crash.

   [SCREENSHOT HERE]

Any error in the SQL query causes the application to crash. This occurs no
matter how tiny the mistake. Even forgetting to put quotes around a string
value is enough to throw an error.

You should expect users to make mistakes in any form. Your program must be able
to survive these errors AND provide feedback to the user about what they did
wrong.

Catch SQL Syntax Errors
-----------------------

As shown above, if a user enters some invalid syntax in the form, the
application crashes. While it is possible to check a SQL string before calling
``.execute()``, this requires a rather large amount of code. Fortunately, there
is a nifty shortcut we can use instead.

Update the ``execute_query()`` function as follows:

.. sourcecode:: Python
   :lineno-start: 11

   if "select" in query_string.lower():
      try:
         results = list(cursor.execute(query_string))
      except:
         results = 'error'

.. index:: ! try/except

This demonstrates how to use a **try/except** block. Python *tries* to run the
code on line 13. If ``query_string`` contains no mistakes, ``.execute()`` runs
fine, and ``results`` is assigned data from the table.

If ``query_string`` is incorrect, ``.execute()`` throws an error. However,
instead of crashing, Python moves to the ``except`` clause and runs the code
there! The ``try/except`` block *prevents the program from crashing* by
providing an safe, alternative set of code. In this case, it assigns the
``'error'`` string to ``results``.

Cool! ``try/except`` saves you some time, since you don't need to do a detailed
check of the SQL string.

Apply this to the else block as well:

.. sourcecode:: Python
   :lineno-start: 8

   def execute_query(query_string):
      db = sqlite3.connect('project.db')
      cursor = db.cursor()
      if "select" in query_string.lower():
         try:
               results = list(cursor.execute(query_string))
         except:
               results = 'error'
      else:
         try:
               cursor.execute(query_string)
               db.commit()
               results = "success"
         except:
               results = 'error'
      db.close()
      return results

Run Test Cases
^^^^^^^^^^^^^^

Test out the new ``execute_query()`` function. Be sure to try valid and invalid
entries in each form.

#. From the home page, select ``INSERT`` and ``movies``. Enter ``title`` in the
   columns box. In the values box, enter the title of your favorite movie.
   IMPORTANT: Put quotes around the movie title.

   If your ``execute_query()`` function works, ``Query successfully executed!``
   should appear below the form. If an error occurred, you will see the message
   ``Sorry, there was a syntax error in your query.``
   
   After a successful ``INSERT``, view the ``movies`` table in Visual Studio
   Code to confirm the new entry.
#. ``UPDATE`` the ``movies`` table to make yourself the director of one of the
   existing films. Once you see ``Query successfully executed``, view the table
   in VS Code to confirm the change.
#. ``DELETE`` a row from the ``directors`` table based on its ``director_id``
   value. Follow this with a ``SELECT`` query to confirm the change.

Continue testing your application until you are comfortable with how it works.

Update ``select_query`` Function
--------------------------------

Want to display column headings...

Deal with '*' entry...

Bonus
-----

Add CSS styling to make the form(s) look nice.

Case insensitivity for column names...
