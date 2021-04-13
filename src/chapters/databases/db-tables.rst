Database Tables
===============

Lorem ipsum...


Rough Notes
-----------

**Relational databases** store data in tables, which are connected to each
other in a variety of different ways. Tables contain columns and rows of
information, with each column specifying the data type of the information
within, and each row having a unique key. Relational databases provide
flexibility for both expansion of the database and modification of the
relationships between the tables as things change.

In order to access our information, we need to use a tool that can talk to a
relational database. **Structured Query Language** or **SQL** is the main tool
used by programmers to work with these data structures. SQL is a
**Relational Database Management System** or RDMS. We can use SQL to perform
many essential operations on a database, such as adding and removing data.

Diagram of table relationship (e.g. author info vs. book info)...

Diagram of a table. Discuss meaning of rows and columns...

Instead of duplicating entires, add relationships between tables. This way, we
can retrieve the information we want by following the links between the tables.
"Oh, you want the author's b-day, but the book table doesn't have it. Well,
let me follow this link from 'Author' column in the book table to that same
person in the 'authors' table."
