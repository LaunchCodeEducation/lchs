Linking CSS to HTML
===================

To use CSS, we need to apply our style rules to a set of HTML code. There are
three different places to add CSS in an HTML file:

#. **Inline**: The CSS gets placed inside individual HTML tags. This is a good
   place to add some quick, specific styling to a small number of elements.
   
   There is no selector in inline CSS. Instead, the ``style`` attribute is
   used. With inline CSS, the styling rule only applies to that one instance of
   the HTML element.

   .. sourcecode:: html

      <tag style="declaration block">Content...</tag>

#. **Internal**: All CSS style rules are placed within the ``<head>`` element
   at the start of the HTML document.
   
   Internal CSS works great when we have a small number of style rules that
   apply to the whole document. The general syntax is:

   .. sourcecode:: html
      :lineno-start: 3

      <head>
         <title>My Web Page</title>
         <style>
            selector {
               property: value;
               property: value;
               /* Other property assignments */
            }

            selector {
               property: value;
               property: value;
            }

            /* Other CSS rules */
         </style>
      </head>
   
   Note that the syntax for the CSS rules follows the format we used on the
   previous page.

#. **External**: All CSS style rules are placed in a separate file. This
   document only contains CSS code, and it is saved with a ``.css`` extension.

   The external CSS file gets linked to the HTML document in the ``<head>``.
   External CSS is great for when we have large amounts of rules that apply to
   the whole page. We can also *reuse* an external CSS document by linking it
   to multiple webpages. The general syntax is:

   .. sourcecode:: html
      :linenos:

      <head>
         <title>My Web Page</title>
         <link rel="stylesheet" type="text/css" href="styles.css">
      </head>

   Let's step through what's going on in line 3:

   #. ``link`` is an HTML tag that tells the browser to connect the webpage to
      what is inside a named file.
   #. ``rel`` describes how the link *relates* to the page. In this case, the
      linked file provides style instructions, so we set ``rel`` to the value
      ``"stylesheet"``.
   #. ``type`` tells the browser what kind of content is saved within the
      linked file. ``type`` should be set to ``"text/css"`` for all style
      sheets. This tells the browser to expect CSS syntax when it opens the
      file.
   #. ``href`` provides the path to the CSS document as well as its name. The
      path tells the browser where to look for the file it needs to open.
      
      In this case, ``href="styles.css"`` tells the browser, "Look in the same
      folder as the HTML file, and open the document called ``styles.css``."

      .. admonition:: Note

         The ``href`` path can describe where a file is stored on a computer,
         or it can be a web address where the CSS code can be accessed.

Order of Precedence
-------------------

Because there is an order of precedence to the location of CSS, it is important
to be able to add or change CSS in all three locations.
Programmers use this to their advantage if they want to be very specific with
overwriting some CSS for one element.
Inline CSS is highest in precedence with internal CSS being next and then
external CSS is lowest.

Inline > internal > external

id > class > element

inner style > outer style

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
