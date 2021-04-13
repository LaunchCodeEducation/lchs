What are Databases?
===================

In the previous chapter, we learned how to use sessions to store data on a
user's device. This allows us to make the information persist after refreshing
a web page or stopping and restarting our Flask app. However, the data is still
temporary. It will be lost when the user closes their browser or clears their
cookies.

In this chapter, we will learn how to store data in a more permanent way. We
will also keep the data off of users' machines. This gives us greater control
over sensitive information.

.. index:: ! database

A **database** stores information and organizes it in a specific way. Unlike
cookies, which contain a single key/value pair, databases allow us to manage a
huge amount of content.

Databases remain separate from both the web server and a user's computer. The
diagram below shows how a database fits in with the server and browser.

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

Note that users don't have direct access to the DB. This allows the web server
to intercept HTTP requests and filter out anything that might corrupt the data
or access it without permission...

Notice that a web browser (the client) can only interact with the web server.

The controller's job is to wait for HTTP requests to come in from different
browsers, then create specific HTTP responses. This usually involves sending
out an update to the *view*...

In the Flask applications we have built, ``main.py`` serves as the controller.
The controller isn't the web server. Instead, it is the program that determines
how the server operates.

The DB server (also called the **model**) runs a separate set of code to
manage data. The program is specifically designed to access the DB and create
new entries, retrieve information, update exiting data, or delete content that
is no longer needed.

Lorem ipsum...

Communicating With a Database
-----------------------------

Just like the conventions in Python and other languages, the structure for
databases follows its own set of rules. To interact with this structure,
programmers use a language called **SQL**.

SQL definition...

.. admonition:: Fun Fact

   Are you a Marvel or DC person? How about Hufflepuff vs. Ravenclaw?

   People pronounce ``SQL`` one of two ways, either like the word "sequel" or
   by sounding out each letter, "ess-que-ell". Both ways are acceptable, but
   some programmers hold very strong opinions about which one to use. Here's a
   handy cheat sheet to keep you out of trouble:

   #. **Pronounced "SQL"**: Yep! 🙂
   #. **Pronounced "SQL"**: Nope! 😡

Use a specific language, SQL, to manage DB content...

Will import that functionality from a Python library/module...

Reference to W3Schools SQL tutorial, for those that are interested...
