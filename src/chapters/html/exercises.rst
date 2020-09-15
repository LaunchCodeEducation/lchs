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
#. Change the font for one of the paragraphs with
   ``style="font-family:Brush Script MT"``, then play around by trying other
   font names like ``Helvetica``.
#. Use the ``style`` attribute to align the ``small`` text to the right edge of
   the screen.

Part 4: Other Semantic Tags
---------------------------

The editor below contains an image and some text, which you can use to practice
with other useful tags and attributes.

Image Attributes
^^^^^^^^^^^^^^^^

Inside the ``<img>`` tag, add the ``width="value"`` or ``height="value"``
attribute to change the size of the image. ``value`` refers to a number of
pixels. Start with a value of ``200`` and then experiment by moving up and down
from there.

.. admonition:: Note

   If both ``width`` and ``height`` are used, the image resizes to their
   values. If only one or the other is added to the ``img`` tag, the image
   will scale to keep the same proportions as the original.

The ``src`` attribute references an image saved in the same folder as this HTML
file. You cannot see the folder in the embedded editor, but X images are
available. Feel free to change the number in ``pet_1.jpg`` to change which
picture gets displayed.

.. admonition:: Warning

   The ``src`` attribute also accepts the address for any image on the web.
   However, pulling images from other sites to display on your own may violate
   copyright laws.

   Discuss with your teacher how to properly cite or request permission to use
   images that don't belong to you.

Special Text Tags
^^^^^^^^^^^^^^^^^

#. In your math and science classes, you use *superscripts* or *subscripts* to
   correctly express chemical or mathematical formulas.

   .. admonition:: Examples

      .. raw:: html

         <h4>Subscripts: 2H<sub>2</sub> + O<sub>2</sub> &rarr; 2H<sub>2</sub>O</h4>

         <h4>Superscript: ax<sup>2</sup> + bx + c = 0</h4>

   To make the ``2`` (or any other character) appear smaller and below the main
   line of text, wrap it with the ``<sub></sub>`` tags. For superscripts, use
   the ``<sup></sup>`` tags instead.

#. In the editor, add some subscripts and superscripts into the text.
#. Next, replace a set of ``<p>`` tags with ``<blockquote>``. What happens?
   This tag is often used to set apart quotes taken from books, movies, plays,
   etc.

Details, Details
^^^^^^^^^^^^^^^^

Sometimes, you want to display information on a webpage only when the user
clicks in a specific spot. One way to accomplish this is by using the
``details`` element.

Paste this code into the editor:

.. sourcecode:: html
   :linenos:

   <details>
      <p>Some text here...</p>
      <p>Some more text here...</p>
      <ul><em>List of items:</em>
         <li>One list item</li>
      </ul>
   </details>

#. What does the ``details`` element do on the screen?
#. Change the first ``<p></p>`` tags in the element to ``<summary>``. What
   happens?
#. Add more content in the ``details`` element describing how you might use it
   on a webpage.
