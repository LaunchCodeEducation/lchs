Project: Movie SQLs
===================

In this chapter, we assigned different string values to a ``sql_query``
variable and used that to execute SQL commands. For the short practice
examples, this worked well. However, we do need a better way to create and run
our queries. After all, we don't want to rewrite our code every time we need to
interact with the database!

In this project, you will design a web form to help build ``sql_query``
strings. These queries will work on two tables stored in a database: ``movies``
and ``directors``.

You won't actually execute any SQL commands here. That is the purpose of the
next chapter. Instead, your goal right now is to *prepare the user interface*.

Why No SQL Queries Yet?
-----------------------

Well, for one thing, you already practiced SQL queries in the
:ref:`chapter exercises <db-exercises>`. Repeating the same tasks here would be
overkill. Now is a good time to review your HTML, CSS, and Flask skills.

Second, ``Movie SQLs`` is a *large and detailed* project. The instructions
won't fit on a single page! You will design the web form here and use that as a
starting point for the bigger task.

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

Project Setup
-------------

#. Open your ``local_practice`` directory in Visual Studio Code. Clone a copy
   of the starter code from this `GitHub repository <https://github.com/LaunchCodeEducation/LCHS_movie_sql_project>`__.
#. Use the *File* menu to open ``LCHS_movie_sql_project``.
#. Follow the usual procedure to create a new virtual environment, activate it,
   and install Flask. If you need a reminder for how to do this, the ``README``
   file contains a summary of the process.
#. Add the name of your virtual environment to the ``.gitignore`` file.
#. The project file tree should now look something like the figure below. If
   you gave a different name to your virtual environment, it will appear
   instead of ``movie-env``.

   .. figure:: figures/db-project-tree-start.png
      :alt: File tree showing 4 folders, 6 templates, main.py, style.css, .gitignore, and a README file.

      For this project, you will work with ``main.py``, six template files, and ``style.css``.

#. Run ``main.py`` to check that everything is OK so far. The application opens
   to a home page:

   .. figure:: figures/db-project-home.png
      :alt: The index.html page, showing a form to select the type of SQL query.
      :width: 70%

      The form lets users select the type of SQL query and the table to access.

#. Use ``git status/git add ./git commit -m`` to begin a version control
   record. If you have your own GitHub account, take a moment to push the
   repository up to the site.

The application runs, but it doesn't do much yet. Let's take a moment to
explore what works right now.

The Home Page (``index.html``)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. index:: ! gateway page

The main page for the application gives users four options to choose from, plus
a dropdown menu to select a table. ``index.html`` serves as a **gateway page**.
Its job is to direct users to different templates based on the SQL query they
want to run.

Select one of the CRUD operations, pick a table, and then click *Submit*. You
will be redirected to a different page and web form. Do this for all four of
the options.

.. admonition:: Tip

   If you're curious about how the gateway page operates, check out the
   comments included with the ``index()`` function in ``main.py``.

   The ``index.html`` template also includes comments describing how the page
   is put together.

Some of the pages are more complete than others, and your job will be to fill
in the missing pieces. You will begin with the easiest page.

Be sure to follow the recommended order! Each task asks you to do a little more
than the one that came before.

The DELETE Form
---------------

From the home page, select ``DELETE`` and the ``Movies`` table. This will
redirect you to the one *complete* form in the starter code.

.. figure:: figures/delete-form.png
   :alt: The DELETE form, with one input box for the WHERE condition.
   :width: 40%

   With the DELETE form, users submit a condition for the ``WHERE`` clause.

Try typing something into the input box, then submit the form. Nothing seems to
happen, because the ``delete()`` function in ``main.py`` is almost empty. Your
job is to add code to the function that will:

- Request data from the form.
- Build a correctly formatted ``sql_query`` string based on that input.
- Render the page again, but with the ``sql_query`` string displayed
  underneath the form.

  .. figure:: figures/delete-form-function.png
     :alt: Lorem ipsum...
     :width: 80%

     The ``delete()`` function in ``main.py`` should build a properly formatted SQL query.

#. Open ``main.py`` and add this code inside the ``delete()`` function.

   .. sourcecode:: Python
      :lineno-start: 44

      def delete_query():
         if request.method == 'POST':
            pass
         else:
            pass
         return render_template('delete.html', tab_title = 'DELETE query', home = False)

#. Next, add code to collect the ``condition`` text from the form. Also,
   collect the table name from the session cookie.

   .. sourcecode:: Python
      :lineno-start: 44

      def delete_query():
         if request.method == 'POST':
            condition = request.form['condition']
            table = session['table']
         else:
            pass

#. Use the ``table`` and ``condition`` variables to build the string for the
   SQL query. Also, assign the empty string to ``sql_query`` in the ``else``
   clause.

   .. sourcecode:: Python
      :lineno-start: 44

      def delete_query():
         if request.method == 'POST':
            condition = request.form['condition']
            table = session['table']
            sql_query = f"DELETE FROM {table} WHERE {condition}"
         else:
            sql_query = ''
            
#. Finally, use the ``render_template()`` function to pass ``sql_query`` to the
   ``delete.html`` template.

   .. sourcecode:: Python
      :lineno-start: 44

      def delete_query():
         if request.method == 'POST':
            condition = request.form['condition']
            table = session['table']
            sql_query = f"DELETE FROM {table} WHERE {condition}"
         else:
            sql_query = ''
         
         return render_template('delete.html', tab_title = 'DELETE query',
            home = False, sql_query = sql_query)

#. Save your changes. Run ``main.py`` and submit the form several times to
   check your code. Fix any bugs that occur.

Congratulations! The delete form and function are now working. Be sure to save,
commit, and push your work.

.. admonition:: Note

   Don't worry about checking if ``condition`` is properly written. We'll deal
   with that in the next chapter.

The UPDATE Form
---------------

Lorem ipsum...

The INSERT Form
---------------

Lorem ipsum...

The SELECT Form
---------------

Lorem ipsum...

Check ``sql_query`` Strings
---------------------------

When the form is submitted, display these on the same page to check syntax.

Break this into 4 sections, one for each type of query.

Bonus
-----

Add CSS styling to make the form(s) look nice.
