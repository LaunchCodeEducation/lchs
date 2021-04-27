More Database Practice
======================

Lorem ipsum...

Update Table Data
-----------------

By using the :ref:`UPDATE <sql-update-syntax>` query, we can change one or more
entries in a table. Code along with the following video to practice this
technique.

.. raw:: html

   <section class="vid_box">
      <iframe class="vid" src="https://www.youtube.com/embed/cn-tbfyQpbY" frameborder="1" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
   </section>

**Key points**:

#. The ``UPDATE`` query should include a ``WHERE`` condition to identify which
   rows in the table to change. If we leave out the condition, then *every* row
   in the table will be modified.
#. After running the query, use the ``.commit()`` method to confirm the
   changes.
#. THERE IS NO UNDO!

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
