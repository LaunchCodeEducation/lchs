Database Tips
=============

Now that we've learned how to crete and interact with a local database, we are
ready for some of the finer points.

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
   contents of our database open for public viewing and download.

To keep our database separate from version control, we need to add its name to
the ``.gitignore`` file *before* we make a commit. (Recall that we used
``.gitignore`` with our :ref:`earlier Flask projects <create-gitignore>`).

.. admonition:: Try It!

   Let's create a new database file and prevent Git from adding it to the
   repository.

   #. Open your ``database_practice`` directory in Visual Studio Code.
   #. If you don't already have one, use the tools in VS Code to create a
      ``.gitignore`` file.
   #. Open ``.gitignore`` in the workspace and add the name of the database
      you want the version control to ignore.

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

Adding a Primary Key
--------------------

Lorem ipsum...

Linking Tables
--------------

Maybe this is too much for the course?

Link to LC101 Java/C# book?
