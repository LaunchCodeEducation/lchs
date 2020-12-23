Reusing Content
===============

Since the :ref:`HTML chapter <html-chapter>`, we've often pasted a block of
starter code into an empty ``.html`` file. This *boilerplate code* often looks
the same across different pages:

.. sourcecode:: html
   :linenos:

   <!DOCTYPE html>
   <html>
      <head>
         <meta charset="UTF-8">
         <meta name="viewport" content="width=device-width">
         <title></title>
         <link rel="stylesheet" type="text/css" href="style.css">
      </head>
      <body>

      </body>
   </html>

In Visual Studio Code, typing the ``html:5`` shortcut into a blank document
shortens this task, but the same issue remains.

   We're putting the same blocks of code into most of our HTML files.

We can save ourselves a lot of time, and keep our work DRY, by keeping reusable
HTML code in a single file.

A ``base`` Template
-------------------

.. index::
   single: template; base

When we design a website, we often want to use the same menu, navigation bar,
logos, etc. on the different pages. If we define a **base template**, we can
use it to store the HTML for the shared content.

Let's build a base template using the boilerplate code above. We will also
include a page header. Once we finish with this, we'll learn how to import the
content into a different HTML file.

.. admonition:: Try It!

   Start with the boiler plate code. Include the link to the style.css page.

   Discuss ``{% block content %}`` and ``{% endblock %}``...

   Demo idea: Header and footer content/image(s) that we want to appear on every
   page.

Placeholders in the Base
^^^^^^^^^^^^^^^^^^^^^^^^

Add a placeholder to the title tag and in the h1 in the header...

The process is the same as before. Note that we will need to supply a value for
these in each of the templates we render using Flask...

Add a Common Header
^^^^^^^^^^^^^^^^^^^

Block out a section for the page title and background image (LCHS)...

Try It! Add a footer...

Extending From the Base
-----------------------

Remove boilerplate code from checkbox_form.html...

Discuss ``{% extends "base.html" %}``...

Note that we need to add ``{% block content %}`` and ``{% endblock %}`` around
the content we want to insert into the base template...

Multiple Blocks
---------------

Lorem ipsum...

This can be done, but it's beyond the scope of this course.

Include link to the `Jinja2 documentation <https://jinja.palletsprojects.com/en/2.11.x/templates/#template-inheritance>`__.

Video Summary
-------------

Embed Chris Bay's video?

.. raw:: html

   <section class="vid_box">
      <iframe class="vid" src="https://www.youtube.com/embed/VS-1vD81Pdc" frameborder="1" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
   </section>

Check Your Understanding
------------------------

Lorem ipsum...
