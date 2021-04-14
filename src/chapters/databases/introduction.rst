What are Databases?
===================

In the previous chapter, we learned how to use sessions to store data on a
user's device. This allows us to make the information persist after refreshing
a web page or stopping and restarting our Flask app. However, the data is still
temporary. It will be lost when the user quits their browser or clears their
cookies.

In this chapter, we will learn how to store data in a more permanent way. We
will also keep the data off of users' machines, which gives us greater control
over the information.

.. index:: ! database

A **database** stores information and organizes it in a specific way. Unlike
cookies, which contain a single key/value pair, databases allow us to manage a
huge amount of content.

Adding a Database
-----------------

Databases remain separate from both the web server and a user's computer. The
diagram below shows how a database fits in with the server and a browser.

.. todo:: Insert diagram showing the flow between clients, a web server, and a database.

The figure brings in some new vocabulary, and it splits the task of running a
website into three large pieces. Let's take a look at the different sections.

Notice that a browser (the **client**) can only interact with the web server.
It sends HTTP requests to the server and displays the responses on the screen.
This is called the **view**.

Similarly, the database only interacts with the **model**. This is a special
program built to manage data. The model code accesses the database to create
new entries, retrieve information, update exiting data, or delete content that
is no longer needed. The model does NOT communicate directly with any clients.

The **control** is a program that receives HTTP requests and sends back the
responses. It contains code that manages the web server, makes decisions, sends
data to the view, and interacts with the model. The control provides a useful
middle step. It intercepts HTTP requests and filters out anything that might
corrupt the database or access it without permission.

In the Flask applications we've built so far, ``main.py`` serves as the
controller.

.. admonition:: Warning

   News stories pop up frequently about hackers accessing private information
   or companies accidentally posting their customers' data online.
   
   When you attach a database to your web application, you MUST take steps to
   protect the information. Visitors to your website should never have direct
   access to sensitive data.

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

Will import that functionality from a Python library/module...

Reference to W3Schools SQL tutorial, for those that are interested...
