Reusing Content
===============

Since the :ref:`HTML chapter <html-chapter>`, we've often pasted a block of
starter code into an empty ``.html`` file. This *boilerplate code* often looks
the same:

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

We can save ourselves some time, and keep our work DRY, if we keep reusable
HTML code in a single file.

A ``base`` Template
-------------------

.. index::
   single: template; base

When we design a website, we often want the same menu, navigation bar, logos,
etc. to appear on several different pages. If we define a **base template**, we
can use it to store this shared HTML.

Let's build a base template starting with the boilerplate code above. We will
then add a page header. Once we finish with this, we'll learn how to link the
template to different HTML files.

.. admonition:: Try It!

   #. In the ``templates`` folder, create a new file called ``base.html``.
   #. Paste in the boilerplate code found at the top of this page, or use the
      ``html:5`` shortcut to do the same thing.
   #. On line 7, link to the ``style.css`` file:

      .. sourcecode:: html

         <link rel="stylesheet" type="text/css" href="{{url_for('static', filename='style.css')}}">
   
   #. Add a placeholder to the ``title`` element:

      .. sourcecode:: html
         :lineno-start: 6

         <title>{{title}}</title>

   Since we added a placeholder to the base template, we will need to supply it
   with a value. We will see how to do this soon.   
   
Good. This gets our base template started. Now lets add some code inside
``<body></body>``.

A Common Header
^^^^^^^^^^^^^^^

Block out a section for the page title and background image (LCHS)...

Try It! Add a footer...

Pull in Different HTML Code
^^^^^^^^^^^^^^^^^^^^^^^^^^^

Discuss ``{% block content %}`` and ``{% endblock %}``...

Demo idea: Header and footer content/image(s) that we want to appear on every
page.

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
