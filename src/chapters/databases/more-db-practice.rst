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
      <iframe class="vid" src="https://www.youtube.com/embed/cn-tbfyQpbY" frameborder="1" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
   </section>

**Key points**:

#. The ``UPDATE`` query uses the ``SET`` keyword to identify one or more columns
   to change.
#. To identify which rows to change, the ``UPDATE`` query should also include a
   ``WHERE`` condition. If we leave out the condition, then *every* row in the
   table will be modified.
#. Combining ``SET`` and ``WHERE`` identifies which cell(s) in the table to
   change.

   .. todo:: Insert diagram showing row/column intersection.

#. After running the query, use the ``.commit()`` method to confirm the
   changes.
#. *There is no Undo option* after we commit an ``UPDATE`` query.

Delete Data
-----------

Code along with the following video to practice removing rows from a table, or
deleting an entire table from the database.

.. raw:: html

   <section class="vid_box">
      <iframe class="vid" src="https://www.youtube.com/embed/CDVGJWiDQI8" frameborder="1" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
   </section>

**Key points**:

#. By using the :ref:`DELETE FROM <sql-delete-syntax>` query, we remove selected
   rows from a table.
#. THERE IS NO UNDO.
