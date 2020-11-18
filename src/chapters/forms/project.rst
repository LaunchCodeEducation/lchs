Project: Search Form (Part 1)
=============================

Introduction
------------

In this chapter and the next, you will build a *search engine selector*. This
consists of a form where the user enters a topic and then chooses which search
engine to run.

A basic search engine selector looks something like this:

.. todo:: Insert image here (basic search engine selector).

Most search engines work the same way. They use a single text input, and they
submit data using a ``GET`` request. Also, many of the most popular engines use
the character ``q`` to indicate the search parameter.

.. admonition:: Try It!

   Use 2-3 different engines to search for *Recent NASA Images*. On the each
   result page, look at the URL in the address bar. If the search engine used a
   ``GET`` request, you should see the ``?`` and ``q`` characters included. You
   will find your query listed as ``q=recent+nasa+images``.
   
   Each engine adds extra characters into the address, so you will need to
   examine the URL carefully.

   **Examples**:

   #. Google: ``www.google.com/search?source=hp&ei=hme1X-K2NMnRtQaKgarYDw&q=recent+nasa+images``
   #. DuckDuckGo: ``duckduckgo.com/?q=recent+nasa+images``
   #. Bing: ``www.bing.com/search?q=recent+nasa+images``
   #. Ask: ``www.ask.com/web?o=0&l=dir&qo=homepageSearchBox&q=recent+nasa+images``

The fact that most search engines use the name ``q`` for their search boxes
allows us to create a form that sends a search request to specific engine.

In Part 1 of this project, you will build the form for your search engine
selector. You will also test it with the *Parrot Server* to verify that it
sends out the correct data.

In Part 2 of this project, you will write some Python code that will collect
the form data, use it to select the proper search engine, and then run the
search request with that engine.

Getting Started
---------------

1. Go to the `studio repository <https://github.com/LaunchCodeEducation/HTTP-and-Forms-Studio/>`_ and fork to your Github account.
2. Clone the repository and ``cd`` into the new directory.

.. admonition:: Note

   We remarked previously that most forms use ``POST`` because they cause data
   to be changed on the server. A web search only *retrieves* data. It does not
   change data. Therefore it's safe to use a ``GET`` request for searches.

Create Form Inputs
------------------

Let's build out the form in ``index.html``. We will need some data for the
search engines we want to work with.

.. list-table:: Search Engine Options
   :header-rows: 1

   * - Label
     - Value
     - Search URL
   * - Google
     - ``google``
     - https://www.google.com/search
   * - DuckDuckGo
     - ``duckDuckGo``
     - https://duckduckgo.com/
   * - Bing
     - ``bing``
     - https://www.bing.com/search
   * - Ask
     - ``ask``
     - https://www.ask.com/web

#. Create a text input within the form and set its ``name`` attribute to the
   value ``"q"``.
#. Create a radio group with one radio button for each search engine. Recall
   that radio buttons with the same ``name`` are grouped, so use the same
   value for this attribute, ``"engine"``, on each radio button.
#. Create a ``label`` element for each radio button.
#. Finally, add a submit button to the form and set it's ``value`` to
   ``"Go!"``.

Test Form Submission
--------------------

Lorem ipsum...

Style the Form
--------------

Lorem ipsum...
