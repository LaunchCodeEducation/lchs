Exercises: CSS
==============

We built a website for you to test your CSS knowledge!

.. todo:: Add links to repl.it and Trinket starter code.

For the exercises, add the following style rules to the website. It's OK to
look back in the chapter, but try to complete as many of the tasks as possible
before you check!

External CSS
------------

#. Change the background color of the whole page to yellow.
#. Change the text color to green for all paragraphs.
#. Change all ``h1`` elements to 36px font size and ``h2`` elements to 24px.
#. Align all text to the center of the page.
#. Let's say that you don't like aligning all of the text to the center. Use a
   CSS class to align only the headings to the center of the page.
#. Create a class called ``fancy-script`` with a ``font-family`` of 
   ``cursive``. What happens when you apply this class to a section, a
   paragraph, or a heading?
#. Can you place more than one value in the ``class`` attribute, like
   ``class="class_name_1 class_name_2"``? Try it to find out!
#. Change the font color of the element with ``id="cool-text"`` to blue. 
#. Use a CSS ``id`` to change the items in the ordered list to a color of
   your choosing.

Internal CSS
------------

#. Add an internal ``p`` selector that sets the ``font-family`` to
   ``Helvetica`` and the text color to ``slategray``.

   a. Does the internal element selector override the external one?
   b. Check ``<p class="fancy-script">``. Does the internal element selector
      override the external class?

#. In ``head``, move the ``<link>`` element below the closing ``</style>`` tag.
   Does changing the order of the two elements matter?
