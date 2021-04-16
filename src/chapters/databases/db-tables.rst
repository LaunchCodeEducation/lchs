Database Structure
==================

Databases store information in **tables**. These are arranged in *columns* and
*rows*. Each column represents a specific piece of data. Every row represents
a single entry in the table.

.. figure:: figures/db-table.png
   :alt: Database tables organize information into rows and columns.
   :width: 80%

   Each row is one entry. Every entry consists of multiple data values, arranged in columns.

**Points to note**:

#. Each column holds a particular data type, like integers, strings, lists,
   etc. All values in a column must be the same data type.
#. Each column also has a label that tells us what the data represents. For
   example, one column might have a ``Last Name`` label, while another could be
   called ``Email``.
#. Each row includes a unique *key*, which helps us manage the data.
#. When we *add or remove* an entry, we create or delete an entire row.
#. When we *change* an entry, we modify the value in one or more columns of a
   single row.

The number of entries in a table is equal to the number of rows. The number of
data values for each entry matches the number of columns.

Relationships Between Tables
----------------------------

Imagine you visit the website for your local library, which uses a program
to operate the online catalog. To find a book, you can search for its title,
the author, a keyword, etc. Given the huge number of books available, the
library database stores a massive amount of information. How is this organized?
Let's consider one possibility.

Assume that the database uses one table, called ``Books``. Each row corresponds
to one title, and the columns include things like the author's name, the
publication date, the number of pages, a short summary, whether the book is
available or checked out, etc. This seems fine, until we need consider data
that users might want to know, but that doesn't relate to an actual title.

For example, let's day we want to read an author's biography. Where would we
put that information in the table? We could add a column called ``Author Bio``.
However, now we've got to repeat that information for every book the author has
written. We're making extra copies of the same data in our storage space!

Also, what if we want to see a list of books an author has written? We could
write some code to loop through the ``Books`` table and find any title written
by the individual. Since there are thousands of books in the database, the
search will take time. In fact, even if an author only has one book, we'd still
need to search through ALL of the table rows to make sure. That is not very
efficient.

The answer to these issues is to save multiple tables in the same database.
For our library, this could include tables for ``Authors``,
``New Arrivals``, ``Science Fiction``, and yes, ``Books``. Each table contains
data that relates only to one idea. The authors' names and biographies stay in
one table, and this remains separate from any book details.

A key piece to the idea of using multiple tables is to create links between
them. We call these links *relationships*.

Instead of duplicating data values, adding relationships between tables lets us
keep ONE copy of the information. If we need information about an author, the
program can retrieve it by following a link between the ``Books`` and
``Authors`` tables.

.. index::
   single: database; relational

**Relational databases** store data in a series of connected tables. Relational
databases provide flexibility for both expansion of the database and
modification of the relationships between the tables as things change.

.. todo:: Diagram of a DB table relationship (e.g. author info vs. book info).
