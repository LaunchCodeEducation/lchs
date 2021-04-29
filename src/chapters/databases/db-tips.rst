Database Tips
=============

Now that we've learned how to crete and interact with a local database, we are
ready for some of the finer points.

Close the Connection
--------------------

In each of the examples in this chapter, we started our Python programs by
opening a connection to the database.

.. sourcecode:: Python

   database = sqlite3.connect('practice.db')

Once connected, we performed several CRUD operations, and then our programs
stopped. When a program ends, the connection to the database automatically
closes.

However, we could easily build a program that uses a loop to keep itself
running. Our Flask applications are good examples of this. They wait for user
input before executing tasks, but they are still running! If we connect to a
database in one of these programs, that connection stays active. This opens up
some possible security issues.

To help prevent unauthorized access to the database, one excellent habit is to
*close the connection* immediately after we finish a CRUD operation.

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

Don't Track the Database with Version Control
---------------------------------------------

Recall that the Git version control system lets us track the changes we make
to our projects. Unless we are careful, *this includes the database file*.

While including the database in a Git repository might seem like a good idea,
we must absolutely avoid doing so! Here are two important reasons why:

#. As we add more information to it, the database eventually becomes very
   large. This increases the size of the repository, which makes it more
   complicated and time consuming to backup.
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
         cursor = database.cursor()

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
two rows in the table can have the same primary key.

By adding primary keys, every row in the table will be different from every
other row. For example, if we have two students with the same name, their table
entries can easily be confused. However, by adding a unique primary key, no two
rows will ever be identical.

.. admonition:: Example

   Compare the rows from two ``students`` tables. Do the entries on the left
   show the same student entered twice? We cannot say for sure. However,
   including a primary key prevents duplicate entries. The table on the right
   implies that we have two different Bobs in our class.

   [INSERT IMAGE]

Assigning primary keys to a table can be done automatically. However, we must
include some special syntax when we first create the table.

.. sourcecode:: SQL

   CREATE TABLE table_name (key_name INTEGER PRIMARY KEY, column_2, ...)

Syntax description...

By default, automatically increments the integer value and prevents duplicate
key values...

Finds largest primary key value (even if gaps exist) and assigns the next higher
value to the next entry.

``authors`` table with ``auth_id`` primary auto-increment...

Use loop to add rows to table. Data comes from list/dictionary...

Try It! box...
