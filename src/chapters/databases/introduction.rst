What are Databases?
===================

In the previous chapter, we learned how to use sessions to store data on a
user's device. This allows us to make the information persist for a longer
period of time. However, the data is still temporary. It will be lost when the
user closes their browser or clears their cookies.

Our next step is to learn how to store data for a long period of time. We also
need to maintain control of the data by keeping it off of users' machines.

.. index:: ! database

A **database** stores information and organizes it in a specific way. Unlike
cookies, which contain a single key/value pair, databases allow us to manage a
huge amount of content.

Databases remain separate from both the web server and a user's computer. Let's
take a look at how this fits in with the interactions between a browser and the
web server.

.. todo:: Insert diagram showing the flow between clients, a web server, and a database.

**Vocabulary**:

#. The **client** is the user's device, which runs a web browser.
#. The **view** represents what the user sees on their screen
#. The **control** is the web server. It is a program that manages HTTP
   HTTP requests and responses. It contains code that makes decisions,
   retrieves data, or...
#. The **model** is another type of server. However, it does NOT communicate
   with any clients. It interacts with the database and the controller to
   manage the flow of data.
#. Lorem ipsum... (database info?)

Examples of Databases
---------------------

Lorem ipsum...
