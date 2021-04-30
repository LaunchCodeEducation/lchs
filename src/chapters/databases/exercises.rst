Exercises: Databases
====================

In these exercises, you will perform several CRUD operations with a new
database file.

Part A: Database Setup
----------------------

Return to ``database_practice`` directory...

Add DB name to gitignore...

Import sqlite3...

Open connection...

In the file tree, right-click on the database name and select *Open database*.

Ready to go!

Part B: Table Setup
-------------------

Imagine that you want to apply your new database skills to bring some order to
your garden. For these exercises, you will use a ``seeds`` table to store some
information. The table will need 4 columns:

- ``seed_id``: This is the primary key assigned to each row in the ``seeds``
   table.
- ``crop``: Identifies what the seeds grow (e.g. yellow bell peppers).
- ``benefit``: Describes the advantages of planting the crop (e.g. nitrogen
   fixation, attracts bees, etc.)
- ``use_by``: The year the seeds expire.

The ``crop`` and ``benefit`` columns will hold ``TEXT`` data types.
``seed_id`` and ``use_by`` will be integers.

#. Define a ``sql_query`` variable, and assign it a string to create the
   ``seeds`` table. Be sure to include the ``PRIMARY KEY`` syntax for the
   ``seed_id`` column.
#. Use ``cursor.execute()`` to run the SQL query and create the new table.
#. Verify that the table was created by expanding the database name in the
   *SQLITE EXPLORER* tab.

   [INSERT SCREENSHOT]

Create
------

For this section, you will be able to reuse the same ``INSERT`` string for each
of the SQL queries.

#. Assign a new string value to your ``sql_query`` variable. It should use the
   ``INSERT INTO`` keywords to add a new entry to the ``seeds`` table. For this
   row, the ``crop`` should be "Agastache", the ``benefit`` is "Attracts bees
   & hummingbirds", and the ``use_by`` year is 2022.

   Notice that you do NOT need to include a value for ``seed_id``, since the
   ``sqlite3`` module will automatically assign primary key values.
#. Re-use the same ``sql_query`` string to add another new entry to the
   ``seeds`` table. This time, choose your own values for the columns.
#. To add values to only *some* of the columns of the table, simply leave out
   those column names and values from the SQL command.

   Add 3 - 5 more rows to the ``seeds`` table. Make sure that some of these
   entries include values for all of the columns, while the rest do not.
#. Finish off your code with a ``.commit()`` statement, then ``.close()`` the
   connection to the database.
#. Run your program, then use the *Play* button in the *SQLITE EXPLORER* tab
   to view the ``seeds`` table.

.. admonition:: Note

   Notice that ``NULL`` gets stored in a cell whenever a value for that column
   is not supplied.

Read
----

For this section, you will need to use several different query strings to
complete the steps.

#. Use ``SELECT ... FROM ...`` to return results from all of the columns in the
   ``seeds`` table.

   Use ``list()`` to convert the returned results, then print the data to the
   console in a clear fashion. *Tip*: Define a function to accomplish this.
#. Repeat step 1, but return and print a single entry based on its ``seed_id``
   value. You will need to include a ``WHERE`` in your SQL query.
#. Repeat step 1, but print list ONLY the ``crop`` data from the table.
#. Select the ``crop`` and ``use_by`` data, but print the results in
   *DECREASING* order by year.

Update
------

Open up a new query tab for the SQL commands you code in this section.

.. admonition:: Warning

   The general syntax for a SQL update is:

   .. sourcecode:: bash

      UPDATE table_name
      SET column1 = newValue1, column2 = newValue2, ...
      WHERE condition;

   If you leave out the ``WHERE`` clause, then *ALL* records in the table will
   be updated!

#. Update a single record based on its ``seed_id``.

   a. The first entry we added in the Create section has ``seed_id`` = 1. Use
      ``UPDATE ... SET ... WHERE`` to change the ``use_by`` date for this entry
      to 2024.
   b. Use a single ``UPDATE`` statement to change two columns for the entry
      with ``seed_id`` = 4.

#. Use ``ALTER TABLE`` to add a new column, called ``expired``, to the table.
   Set the data type to ``boolean``.
#. With a single ``UPDATE`` command, set the ``expired`` value to ``true`` for
   all entries that have a ``use_by`` of this year or earlier.

Be sure to list the ``seeds`` table to confirm your changes.

Delete
------

Open up a new query tab for the SQL commands you code in this section.

.. admonition:: Warning

   If you leave out the ``WHERE`` clause in the ``DELETE FROM`` command, then
   *ALL* records in the table will be lost!

   There is no undo option after running ``DELETE``.

#. Delete a single record from the table. Be sure to use its ``seed_id`` rather
   than any other column value in the ``WHERE`` clause.
#. Use a single ``DELETE`` command to remove any seeds from the table that have
   expired.

Bonus Exercises
---------------

Whew! You made it through all the exercises. Nice work!

Take a quick break and, if you wish, try these additional tasks that go above
and beyond the basic SQL commands.

#. Use logical operators (``AND``, ``OR``, ``NOT``) in ``WHERE`` statements.
#. List the complete records for the seeds, but only if the ``encourages``
   column ``IS NOT null``.
#. Do you have several entries with the same ``crop`` value? If so, you can
   display a list that avoids repeats by using the `SELECT DISTINCT <https://www.w3schools.com/sql/sql_distinct.asp>`__
   keywords.
#. Experiment with `changing the data type <https://www.w3schools.com/sql/sql_alter.asp>`__
   of a column.
#. Research the difference between ``DROP DATABASE table_name`` vs.
   ``DELETE FROM table_name``.
