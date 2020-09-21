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

#. **Internal**: All CSS style rules occur in one location inside the HTML
   file. The rules are placed within the ``<head>`` element at the start of the
   document.
   
   Internal CSS works great when we have a small number of style rules that
   apply to the whole document. The general syntax is:

   ::

      <head>
         <title>My Web Page</title>
         <style>
            selector {
               declaration block
            }

            selector {
               declaration block
            }

            selector {
               declaration block
            }
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
      what is inside the named file.

   
   
   ``rel``, ``type``, ``href`` are all HTML
   attributes that are required to properly link CSS and let the browser know
   that CSS is what is in the file and where the file is.
   ``rel`` should be set to "stylesheet", because it designates how the link relates to the page. ``type`` will be set to "text/css" for all stylesheets.
   ``href`` is where the programmer enters the path to the stylesheet that should be used for the page.

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
