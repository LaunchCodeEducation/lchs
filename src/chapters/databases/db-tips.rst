Database Tips
=============

Now that we've learned how to crete and interact with a local database, we are
ready for some of the finer points.

Close the Connection
--------------------

In each of the examples in this chapter, we start by opening a connection to
the database.

.. sourcecode:: Python

   database = sqlite3.connect('practice.db')

Once connected, we perform several CRUD operations, and then our programs stop.
Each time our programs end, the connection to the database automatically
closes.

However, we can easily build a program that uses a loop to keep itself running.
Our Flask applications are good examples of this. They wait for user input
before executing tasks, but they are always running! If we connect to a
database in one of these programs, that connection stays active. This opens up
some potential security issues.

To help limit access to the database, one excellent habit is to
*close the connection* immediately after we finish a set of CRUD operations.

The syntax for closing a connection is quite simple:

.. sourcecode:: Python

   database.close()

This statement should be placed right after the execution of our SQL queries.

By deliberately closing the connection, the flow for our database interactions
looks something like this:

#. Open a connection to the database.
#. Execute one or more SQL queries, and use ``.commit()`` as needed.
#. Close the connection.

Every time we access the database, we must re-open the connection, execute our
SQL queries, and then close the connection. While it might seem inefficient to
continually open and close the database connection, this is the safer option.
Access to the data is only available when we need to perform CRUD operations.

This structure also fits well with splitting jobs across different Python
functions.

Don't Track the Database with Version Control
---------------------------------------------

Recall that the :ref:`Git version control system <git-chapter>` lets us track
the changes we make to our projects. Unless we are careful,
*this includes the database file*.

While including the database in a Git repository might seem like a good idea,
we must absolutely avoid doing so! Here are two important reasons why:

#. Over time, the size of the database can become very large. This increases
   the size of the repository, which makes it more complicated and time
   consuming to backup.
#. If the database is part of the repository, it will be visible to *anyone*
   who has access to the repo. If we push the repo to GitHub (where saved
   projects are visible to anyone with a web browser), then we make the
   contents of our database open for public viewing and download. (This is
   bad).

To keep our database separate from version control, we need to add its name to
the ``.gitignore`` file *before* we make a commit. (Recall that we used
``.gitignore`` with our :ref:`earlier Flask projects <create-gitignore>`).

.. admonition:: Try It!

   Let's create a new database file and prevent Git from tracking it as part of
   the repository.

   #. Open your ``database_practice`` directory in Visual Studio Code.
   #. If you don't already have one, use the tools in VS Code to create a
      ``.gitignore`` file.
   #. Open ``.gitignore`` in the workspace and add the name of the database
      you want Git to ignore.

      .. sourcecode:: python
         :linenos:

         no_gitting_this.db

      If you have an existing ``.gitignore`` file, you can add the database
      name anywhere in the file. The name just needs to be on its own line.

   #. Open ``main.py`` and create the new database file. Its name must match
      the one in ``.gitignore``.

      .. sourcecode:: python
         :linenos:

         import sqlite3

         database = sqlite3.connect('no_gitting_this.db')

   #. Run ``main.py``. Notice that when the new database appears in the file
      tree, its name remains gray.

      .. figure:: figures/db-ignore.png
         :alt: Showing the file tree with database names greyed out.

   #. Run ``git status`` in the terminal. Notice that ``main.py`` and
      ``.gitignore`` appear in the output, but not the new database.

      .. sourcecode:: bash

         $ git status
         On branch main
         Changes not staged for commit:
         (use "git add <file>..." to update what will be committed)

            modified:   .gitignore
            modified:   main.py

Add a Primary Key
-----------------

.. index:: ! primary key

To help mange the data stored in a table, one helpful tool is the
**primary key**. This is an integer assigned to each row in the table, and no
two rows can have the same primary key.

By adding primary keys, every row in the table will be different from every
other row. For example, if we have two students with the same name, their table
entries can easily be confused. However, by adding a unique primary key, no two
rows will ever be identical.

.. admonition:: Example

   Compare the rows from two ``students`` tables. Do the entries on the left
   show the same student entered twice? We cannot say for sure. However,
   including a primary key prevents duplicate entries. The table on the right
   implies that we have two different Bobs in our class.

   .. figure:: figures/primary-key.png
      :alt: Showing two database tables. One with a primary key column and the other without.
      :width: 80%

      The table on the right includes an ``id`` column that stores the primary key for each row.

When we use the ``sqlite3`` module, assigning primary keys can be done
automatically. However, we must include some special syntax when we first create
the table.

.. sourcecode:: SQL

   CREATE TABLE table_name (key_name INTEGER PRIMARY KEY, other_columns...)

#. ``key_name`` is the column in the table that will store the primary keys.
   Each key value must be an integer data type.
#. Notice that we must type out ``INTEGER`` instead of ``INT`` for the data
   type. This is required. Using ``INT`` causes errors.
#. ``PRIMARY KEY`` sets up the process to automatically assign an integer to
   ``key_name``. This happens each time a new row is added to the table. We do
   NOT need to assign a value to ``key_name`` ourselves.
#. Python keeps track of the largest primary key in the table. When a new row
   is added, its primary key is assigned the next higher value.
#. We can assign our own value to ``key_name`` when we ``INSERT`` a row.
   However, the action will throw an error if the value we choose matches a
   primary key already in the table.

.. admonition:: Try It!

   ``authors`` table with ``auth_id`` as the primary key...

   Use a loop to add rows to table. Data comes from list/dictionary...

   Delete one row. Notice that the primary keys now have a gap...

   Add new row with specific PK. Note that next automatic row has a PK that
   picks up from the largest existing PK.

   Try inserting a row with a duplicate PK.

#. Return to your ``database_practice`` directory in Visual Studio Code. Open
   ``main.py`` in the editor.
#. Create a new table in ``practice.db`` called ``authors``. The table should
   include 4 columns: ``author_id, last_name, first_name, website``.

   .. sourcecode:: Python
      :linenos:

      import sqlite3

      database = sqlite3.connect('practice.db')
      cursor = database.cursor()

      sql_query = """
         CREATE TABLE IF NOT EXISTS authors 
         (author_id INTEGER PRIMARY KEY, last_name TEXT, first_name TEXT, website TEXT)
         """
      cursor.execute(sql_query)

#. Rather than writing a separate SQL query for each author, we will use a loop
   to do the work for us. Paste this code into the editor:

   .. sourcecode:: Python
      :lineno-start: 13

      # Each list in 'authors' contains the last name, first name, and website values.
      authors = [
         ['Jemisin', 'N.K.', 'https://nkjemisin.com/'],
         ['Willems', 'Mo', 'https://pigeonpresents.com/'],
         ['Alvarez', 'Julia', 'https://www.juliaalvarez.com/']
      ]

      # Assign the SQL query string, including placeholders.
      sql_query = "INSERT INTO authors (last_name, first_name, website) VALUES (?, ?, ?)"
      
      # Loop through the 'authors' list.
      for author in authors:
         last = author[0]
         first = author[1]
         url = author[2]

         # Insert a new row into the 'authors' table.
         cursor.execute(sql_query, (last, first, url))

      database.commit()
      database.close()

#. Run ``main.py``, then use your SQLite extension powers to view the
   ``authors`` table in VS Code. Even though we did NOT include values for
   ``author_id`` in the SQL query, each row still displays a value for that
   column.
#. Delete a row from the middle of the table... View again.
#. Insert a new row, but this time include a value for ``author_id``. View table.
#. Try inserting a row with an ``author_id`` value that already appears in the
   table.
