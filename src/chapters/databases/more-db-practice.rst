More Database Practice
======================

In the previous pages, we created a database, added a table to it, and saved
several entries in that table. Now we will learn how to modify the stored data.

Update Table Data
-----------------

By using an :ref:`UPDATE <sql-update-syntax>` query, we can change one or more
entries in a table. Code along with the following video to practice this
technique.

.. raw:: html

   <section class="vid_box">
      <iframe class="vid" src="https://www.youtube.com/embed/piXiY9j64I4" frameborder="1" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
   </section>

**Key points**:

#. The ``UPDATE`` query uses the ``SET`` keyword to identify one or more columns
   to change.
#. To identify which rows to change, the ``UPDATE`` query should also include a
   ``WHERE`` condition. If we leave out the condition, then *every* row in the
   table will be modified.
#. Combining ``SET`` and ``WHERE`` identifies which cell(s) in the table to
   change.

   .. figure:: figures/table-update.png
      :alt: Showing how SET and WHERE cross in a table to identify the cell(s) to change.
      :width: 80%

      Each cell in the table has a (column, row) position.

#. After running the query, use the ``.commit()`` method to confirm the
   changes.
#. After we commit an ``UPDATE`` query, there is no quick *Undo* option!

**Sample code**:

.. sourcecode:: Python
   :linenos:

   import sqlite3

   database = sqlite3.connect('practice.db')
   cursor = database.cursor()

   # Update selected cells from the 'students' table:
   sql_query = "UPDATE students SET recent_grad = 'No' WHERE grad_year < 2017"
   cursor.execute(sql_query)
   database.commit()

Delete Data
-----------

Code along with the following video to practice removing rows from a table.
Also learn how to delete an entire table from the database.

.. raw:: html

   <section class="vid_box">
      <iframe class="vid" src="https://www.youtube.com/embed/CDVGJWiDQI8" frameborder="1" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
   </section>

**Key points**:

#. The :ref:`DELETE FROM <sql-delete-syntax>` query removes selected rows from
   a table.
#. Add a ``WHERE`` clause to identify which rows should be deleted.
#. The ``DROP TABLE`` query removes an entire table from the database. ALL the
   row and column information will be deleted.
#. *There is NO undo option* for a ``DELETE`` or ``DROP`` query.

**Sample code**:

.. sourcecode:: Python
   :linenos:

   import sqlite3

   database = sqlite3.connect('practice.db')
   cursor = database.cursor()

   # Delete selected rows from the 'students' table:
   sql_query = "DELETE FROM students WHERE recent_grad == 'No'"
   cursor.execute(sql_query)
   database.commit()
   
   # Drop the 'remove_me' table from the database:
   sql_query = "DROP TABLE remove_me"
   cursor.execute(sql_query)

Check Your Understanding
------------------------

Lorem ipsum...

