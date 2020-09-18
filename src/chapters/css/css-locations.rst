Linking CSS to HTML
===================

To get started with CSS, programmers need to add CSS to HTML.

There are three different places to add CSS in an HTML file as indicated above:

1. External: The CSS is in a separate file linked to the HTML document in the ``<head>``. External linking of CSS is great for when programmers have large quantities of CSS that apply to the whole page.

   .. sourcecode:: html
      :linenos:

      <head>
         <title>My Web Page</title>
         <link rel="stylesheet" type="text/css" href="styles.css">
      </head>

   ``link`` is an HTML tag that tells the browser to connect what is inside the linked file to the web page content.
   ``rel``, ``type``, ``href`` are all HTML attributes that are required to properly link CSS and let the browser know that CSS is what is in the file and where the file is.
   ``rel`` should be set to "stylesheet", because it designates how the link relates to the page. ``type`` will be set to "text/css" for all stylesheets.
   ``href`` is where the programmer enters the path to the stylesheet that should be used for the page.

2. Document or internal: All CSS styling is inside the HTML file, but within the ``<head>``. Internal use of CSS is great for when the programmer has a small amount of CSS that applies to the whole document.

   ::

      <head>
         <title>My Web Page</title>
         <style>
            selector {
                declaration block
            }
         </style>
      </head>

3. Inline: Programmers add CSS styling to individual tags. This is a good place to add some specific styling.
   There is no selector in inline CSS; instead, the ``style`` attribute is used. This is because the styling only applies to that one instance of the HTML tag.

   .. sourcecode:: html

      <tag style="declaration block">content</tag>

Order of Precedence
-------------------

Because there is an order of precedence to the location of CSS, it is important to be able to add or change CSS in all three locations.
Programmers use this to their advantage if they want to be very specific with overwriting some CSS for one element.
Inline CSS is highest in precedence with internal CSS being next and then external CSS is lowest.

Try It!
-------

Lorem ipsum...

#. Add new style.css page.
#. Link page to HTML document.
#. Add style info to ``head`` element.
#. Add inline styling.
#. Compare order of precedence.

Check Your Understanding
------------------------

.. admonition:: Question

   What is the order of precedence in CSS?

   #. Internal > External > Inline
   #. Inline > Internal > External
   #. Inline > External > Internal
   #. External > Internal > Inline
