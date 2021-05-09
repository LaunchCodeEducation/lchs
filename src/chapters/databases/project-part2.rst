.. _movie-sql-part-2:

Project: Movie SQLs (Part 2)
============================

Now that each of the CRUD functions creates a ``sql_query`` string, the next
step is to perform those actions! On this page, you will add a new function to
your Python code. Its job is to execute any query string it receives.

Code the ``execute_query`` Function
-----------------------------------

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

   a. Lines 9 and 10 open a connection to the database and initialize the
      ``db`` and ``cursor`` objects.
   b. Line 15 closes the connection to the database after each SQL query.
   c. Lines 11 - 14 will contain the code to run the SQL queries.
#. Note the condition in line 11. If the SQL query calls for a SELECT
   operation, the function should return a list of results from the database.
   Update the code to assign those results to a variable, then return them.

   .. sourcecode:: Python
      :lineno-start: 8

      def execute_query(query_string):
         db = sqlite3.connect('project.db')
         cursor = db.cursor()
         if "select" in query_string.lower():
            results = list(cursor.execute(query_string)) # Read data from project.db.
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
you started. The next step is to run some test queries.

Perfect Syntax
^^^^^^^^^^^^^^

Lorem ipsum...

Caution students to type entries exactly as they appear...

Note that quotes are necessary inside the input boxes for string values...

What happens if there is a syntax error in the SQL query? The program crashes!
We need to deal with this...

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
code on line 13. If ``query_string`` contains no mistakes, ``.execute`` runs
fine, and ``results`` is assigned data from the table.

If ``query_string`` is incorrect, ``.execute`` throws an error. However,
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

Update ``select_query`` Function
--------------------------------

Want to display column headings...

Deal with '*' entry...

Bonus
-----

Add CSS styling to make the form(s) look nice.

Case insensitivity for column names...

Old Notes
---------

The next chapter is an extended walkthrough. You will first add a database to a
Flask application. Then you will replace the hard-coded ``sql_query`` strings
in your Python program with ones built from your web form. You will also use
your Jinja2 template skills to display the results from ``SELECT`` queries.

Each page in the next chapter will add one piece to the Flask application. By
the end, you will have a user interface that runs in the browser. This provides
a more convenient way to add information to a selected table, perform searches,
update existing data, or delete entries.

Yes, the expectations are high. HOWEVER, it's also the end of the course. You
are TOTALLY ready for this challenge!

Let's get started.
