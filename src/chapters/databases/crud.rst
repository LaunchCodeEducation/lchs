Database Operations
===================

For this course, we are not going to create or access a large-scale database.
Instead, we will mimic the behavior of a database by creating a file in our
project directory. This file will contain all the necessary tables, and we will
use it to store and access information.

Before we set up our first database, we need to recognize the four main actions
we will perform with it.

CRUD
----

.. index:: ! query, ! CRUD

.. index::
   single: SQL; query
   single: SQL; CRUD

When we perform an operation on a database, we write a **query**. Queries can
be simple or complex, depending on the task. We can fit each query’s purpose
into one of four categories:

#. Create
#. Read
#. Update
#. Delete

Taking the first letter from each category gives is the term **CRUD**. Let's
look at each type of operation in more detail.

Create
------

When we talk about *creating* something in a database, this can mean adding a
new table, a new row, or a new column.

Adding a Table
^^^^^^^^^^^^^^

When we add a new table to the database, the query must include the
following:

#. A name for the table,
#. A label for each column,
#. The data type for each column.

We will worry about the exact syntax later, but the query looks something like
this:

.. sourcecode:: mysql

   CREATE TABLE table_name (column_name_1 data_type, column_name_2 data_type,...)

Notice that each column name and its data type come as a pair
(``column_name_1 data_type``) and are NOT separated by commas. However, the
different name/type pairs ARE separated inside the parentheses ``()``.

Adding a Row
^^^^^^^^^^^^

Once we have a table ready to go, the query to add a new entry must include:

#. The name of the table,
#. The name of one or more of columns in that table,
#. A value for each of the selected columns.

The general syntax to add a new row looks like this:

.. sourcecode:: mysql

   INSERT INTO table_name (column_1, column_2, ...) VALUES (value_1, value_2, ...)

Lorem ipsum...

Adding a Column
^^^^^^^^^^^^^^^

To add a column to an existing table, the query must include:

#. The name of the table,
#. The name for the new column,
#. The data type for the new column.

The general syntax looks like this:

.. sourcecode:: mysql

   ALTER TABLE table_name ADD COLUMN column_name data_type

When we create a new column in a table, we do NOT need to fill it with any
values. Existing rows in the table will add the new slot but keep it empty.

.. index:: ! NULL

.. admonition:: Note

   Empty spaces in a database are assigned a special value called **NULL**.
   
   ``NULL`` is NOT the same as an empty string, ``0``, or ``False``. ``NULL``
   is literally an empty space, and it indicates that a data value does not
   exist for that spot in the table.

Read
----

To get information from a table, the query must include:

#. The table name,
#. The name of one or more columns.

The query may also include a *condition* to help filter the results.

The general syntax looks like this:

.. sourcecode:: mysql

   SELECT column_name_1, column_name_2, ...
   FROM table_name
   WHERE condition

Update
------

Lorem ipsum...

Delete
------

Lorem ipsum...

Check Your Understanding
------------------------

Lorem ipsum...
