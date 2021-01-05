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
   #. On line 7, use the ``url_for`` function to link to the ``style.css``
      file:

      .. sourcecode:: html

         <link rel="stylesheet" type="text/css" href="{{url_for('static', filename='style.css')}}">
   
   #. Add a placeholder to the ``title`` element:

      .. sourcecode:: html
         :lineno-start: 6

         <title>{{title}}</title>
   
Good. This gets our base template started. Now lets add some code inside
``<body></body>``.

Block Out Space for Other HTML Code
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The goal of ``base.html`` is to store the code we want to use across several
different webpages. Each of these pages will link to ``base``, and the browser
will render the shared code. However, each page will also have content that is
separate from the others.

Inside ``base.html``, we need to add instructions for where we want to insert
new HTML code. Think of ``base`` like a document that contains some holes. Each
webpage that uses ``base`` will put its own content into those holes.

Discuss ``{% block content %}`` and ``{% endblock %}``...

Extending From the Base
-----------------------

Remove boilerplate code from checkbox_form.html...

Discuss ``{% extends "base.html" %}``...

Note that we need to add ``{% block content %}`` and ``{% endblock %}`` around
the content we want to insert into the base template...

A Common Header
---------------

Let's jazz up the page title by putting it into a ``header`` element.

#. Inside ``base.html``, add the following code:

   .. sourcecode:: html
      :lineno-start: 9

      <body>
         <header class="head-background">
            <h1>{{page_title}}</h1>
         </header>
      </body>

#. The ``<header>`` tag includes the ``class`` attribute. We need to define the
   ``head-background`` CSS rule next.
#. Open ``style.css`` and add the following class selector:

   .. sourcecode:: css
      :linenos:

      .head-background {
         padding: 10px 0;
         text-align: center;
         background-image: radial-gradient(#419f6a 60%, #3c79b8 40%);
      }
   
   ``radial-gradient`` allows us to display different colors in a background.

Block out a section for the page title and background image (LCHS)...

Try It! Add a footer...

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
