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
huge amount of content. Think of a database like a large hard drive. However,
its only job is to store information. It runs no programs.

Using a database instead of sessions lets developers decide what information to
save, who can access it, and how long to keep it.

Adding a Database
-----------------

Databases remain separate from both the web server and a user's computer. The
diagram below shows how a database fits in with the server and a browser.

.. todo:: Insert diagram showing the flow between clients, a web server, and a database.

The figure brings in some new vocabulary, and it splits the task of running a
website into three large pieces. Let's take a look at the different sections.

.. index:: ! client, ! view, ! model, ! controller

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

.. index:: ! SQL
   single: SQL; structured query language

To maintain consistency across the world, many companies use the same basic
structure when they set up their databases. To interact with this structure,
programmers use a tool called **SQL**, which stands for *Structured Query
Language*.

.. admonition:: Fun Fact

   Are you a Marvel or DC person? How about Hufflepuff vs. Ravenclaw?

   People pronounce ``SQL`` one of two ways, either like the word "sequel" or
   by sounding out each letter, "ess-que-ell". Both ways are acceptable, but
   some programmers hold strong opinions about which one to use. Here's a handy
   cheat sheet to keep you out of trouble:

   #. **Pronounced "SQL"**: Yep! 🙂
   #. **Pronounced "SQL"**: Nope! 😡

   Really, it doesn't matter! 😉

Learning how to use SQL is a complete course by itself. Fortunately, Python and
Flask provide us with some shortcuts. We will install the necessary libraries
and explore how to use them later in this chapter.

For those who are interested in a good SQL tutorial, `W3Schools <https://www.w3schools.com/sql/default.asp>`__
provides one.

Check Your Understanding
------------------------

.. admonition:: Question

   Visitors to a website can interact with which of the following? Select ALL
   that apply.

   .. raw:: html

      <ol type="a">
         <li><span id = "a" onclick="highlight('a', true)">The view</span></li>
         <li><span id = "b" onclick="highlight('b', true)">The controller</span></li>
         <li><span id = "c" onclick="highlight('c', false)">The model</span></li>
         <li><span id = "d" onclick="highlight('d', false)">The database</span></li>
      </ol>

.. Answers = a, b

.. admonition:: Question

   How long does information remain on a database?

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> Until the user quits their browser.</li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> Until the user clears their sessions/cookies.</li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> For 24 hours.</li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, true)"> Until the developer decides to delete it.</li>
      </ol>
      <p id="Q2"></p>

.. Answer = d
