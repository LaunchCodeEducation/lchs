Database Practice
=================

On this page, we will add rows to the ``students`` table and then learn how to
access and view that data from our Python program.

Add New Entries
---------------

Code along with this video as we add new rows to the ``students`` table.

.. todo:: Insert video showing how to add rows to a database table.

**Key points**:

#. Use the :ref:`INSERT INTO <sql-insert-syntax>` query to add a new row.
#. Notice the ``(?, ?, ?)`` at the end of the query string. The question marks
   serve as placeholders for the values we want to save in the new row.
#. We indicate those values with arguments inside the ``.execute()`` method.
#. Use the ``.commit()`` method to finish the process.

**Final code from the video**:

.. sourcecode:: Python
   :linenos:

   import sqlite3

   database = sqlite3.connect('practice.db')
   cursor = database.cursor()

   sql_query = "CREATE TABLE IF NOT EXISTS students (last_name TEXT, first_name TEXT, grad_year INT)"
   cursor.execute(sql_query)

   last_name = input("Enter your last name: ").capitalize()
   first_name = input("Enter your first name: ").capitalize()
   grad_year = int(input("Enter your graduation year: "))

   sql_query = "INSERT INTO students (last_name, first_name, grad_year) VALUES (?, ?, ?)"
   cursor.execute(sql_query, (last_name, first_name, grad_year))
   database.commit()

Viewing a Table
^^^^^^^^^^^^^^^

We still can't open ``practice.db`` in the editor and view the stored data. To
do this, we need to add an extension to Visual Studio Code. Follow along with
this video to update VS Code:

.. todo:: Insert video showing how to add the SQLite extension to VS Code.

**Cliff Notes**:

#. Click the extensions button in VS Code. Enter ``SQLite`` in the search bar,
   then select and install the extension by ``alexcvzz``.

   .. figure:: figures/sqlite-extension.png
      :alt: The extensions tab, search bar, and extension info for SQLite by alexcvzz.
      :width: 80%

      It only takes about 3 clicks to install the SQLite extension.

#. Right-click on ``practice.db`` and select *Open Database*. At the bottom-left
   of the VS Code workspace, open the *SQLITE EXPLORER* tab. Expand
   ``practice.db``, then click on the *Play* button next to the ``students``
   table.

   .. figure:: figures/view-table.png
      :alt: Showing SQLite Explorer tab, with Play button next to students table.
      :width: 60%

      Click the Play arrow to view the contents of the student table.

Retrieve Data From Table
------------------------

Code along with this video as we access the information in the database and
display it in the console.

.. todo:: Insert video showing how to write and execute a SELECT query.

**Key points**:

Lorem ipsum...

**Final code from the video**:

Lorem ipsum...

Check Your Understanding
------------------------

Lorem ipsum...
