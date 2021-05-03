Project: Movie SQLs
===================

In this chapter, we assigned different string values to a ``sql_query``
variable and used that to execute SQL commands. For the short practice
examples, this worked well. However, we do need a better way to create and run
our queries.

In this project, you will design a web form to help build ``sql_query``
strings. These queries will relate to two tables stored in a database:
``movies`` and ``directors``.

We won't actually execute any SQL commands here. That is the purpose of the
next chapter. Instead, our goal right now is to *prepare the form*.

Why No SQL Queries Yet?
-----------------------

Well, for one thing, you already practiced SQL queries in the
:ref:`chapter exercises <db-exercises>`. Repeating the same tasks here would be
overkill. Now is a good time to review your HTML, CSS, and Flask skills.

Second, ``Movie SQLs`` is a *large and detailed* project. The instructions
won't fit on a single page! You will design the web form here and use that as a
starting point for the bigger task.

The next chapter will be an extended walkthrough. You will first combine a
database with a Flask application. Then you will replace the hard-coded
``sql_query`` strings in your Python code with ones built from your web form.
You will also use a Jinja2 template to display the results from ``SELECT``
queries.

Each chapter page will add one piece to the Flask application. By the end, you
will have a user interface that runs in the browser. This provides a more
convenient way to add new information to a selected table, perform searches,
update existing data, or delete entries.

Yes, the expectations are high. HOWEVER, it's also the end of the course. You
are TOTALLY ready for this challenge!

Let's get started.

Project Setup
-------------

Lorem ipsum...

New project directory (``movie_sql_project``)...

Install venv and Flask. Add starter main.py, index.html, results.html, and
style.css pages...

Add functions to ``main.py`` to render each template. Run the application to
check that everything is OK so far.

Design the Form
---------------

Lorem ipsum...

Basic layout...

Radio buttons for INSERT, SELECT, UPDATE, DELETE...
Already provided? Users select and submit, then redirect to a form for the
chosen option.

Dropdown for table names...

Dropdown/checkboxes for column names...

Check ``sql_query`` Strings
---------------------------

When the form is submitted, display these on the same page to check syntax.

Break this into 4 sections, one for each type of query.

Bonus
-----

Add CSS styling to make the form(s) look nice.
