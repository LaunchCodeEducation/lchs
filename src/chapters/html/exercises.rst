Exercises: HTML
===============

.. admonition:: Note

   If your teacher added you to a :ref:`repl.it classroom <replit-classroom-assignments>`
   or a :ref:`Trinket course <trinket-course-assignments>`, login to your
   account to access the starter code for each exercise.

   If you are NOT enrolled in a repl.it classroom or Trinket course, use one of
   the following links to copy the starter code.

   .. todo:: Insert links to the LCHS Trinket and repl.it starter code files.

Part 1: Add a Few Elements
--------------------------

Complete an ``index.html`` file for a simple webpage:

#. Add an ``h1`` to the page that says "Why I Love Web Development".
#. Add an ordered list to the page. It should include 3 items that describe
   why you are excited about web development.
#. Add a paragraph about the first web page you want to make (or have already
   made) with your web development superpowers!
#. Add a link to an external website below your paragraph.

This code block gives you a rough outline for how it might look.

.. sourcecode:: html
   :linenos:

   <!DOCTYPE html>
   <html>
      <head>
      </head>
      <body>
         <!-- h1 goes here --->
         <!-- ol goes here --->
         <!-- p goes here --->
         <!-- a goes here --->
      </body>
   </html>

.. admonition:: Note

   The starter code contains other HTML inside of the ``head`` element that you
   do not need to modify. Just add code for this exercise, NOT delete!

   Also, when clicking on your link to make sure it works, right-click to open
   it in a new tab!

Part 2: Organize the Elements
-----------------------------

Next, add some semantic tags to organize and expand your HTML file.

#. Add ``<header>`` tags around the ``h1`` element.
#. In the header, include some follow-up text to expand the element. This could
   include one or more subheadings or a short paragraph (``<p></p>``).
#. Below the header, add a ``section`` element that includes a pair of
   ``<article>`` tags.
#. Move the ``ol`` element from Part 1, Step 2 into the article. Add a sentence
   or two to introduce the list.
#. Add a second ``article`` element in the ``section``. Move your paragraph
   from Part 1, Step 3 into this element. Next, add a ``ul`` element that lists
   items you will include on your future webpage.
#. Create a new ``section`` element below the first. Add an ``h2`` heading
   called "Favorite websites", then include at least three links. (You can
   re-use the link from Part 1, Step 4).
   
   .. admonition:: Tip
   
      If want to be fancy, you can place the links in a list.

      .. sourcecode:: html

         <ul>
            <li><a href="...">Link text</a></li>
         </ul>

#. Add a ``footer`` element that includes the name of your school, the name of
   your programming class, and the date. Place ``<small>`` tags around the text
   to reduce the size of the words.
#. (Optional) Look up the entity codes for some fun symbols, then scatter them
   around in your text.

Part 3: Add Attributes
----------------------

Now add attributes to some of the tags to change the look of the text.

#. Use the ``style="color:color_name"`` to change the text color of your
   headings to something other than black.

   - Does adding the style attribute to the ``<h1>`` tag have a different
     effect than adding it do the ``<header>`` tag?

#. Use the ``type`` attribute in the ordered list to change the bullets from
   numbers to lowercase letters. For the unordered list(s), change the bullets
   to ``type="disc"``.
#. For the image, add the ``width="value"`` or ``height="value"`` attribute to
   change the size of the image. ``value`` refers to a number of pixels.

   .. admonition:: Note

      If both ``width`` and ``height`` are used, the image scales to their
      values. If only one or the other is added to the ``img`` tag, the image
      will scale to keep the same proportions as the original.

#. Change the font for one of the paragraphs with
   ``style="font-family:Brush Script MT"``, then play around by trying other
   font names like ``Helvetica``.
#. Align the ``small`` text to the right edge of the screen.

Part 4: Other Semantic Tags
---------------------------

Lorem ipsum...

``details`` element...

``sub`` and ``sup`` elements...

Maybe the ``blockquote`` element...
