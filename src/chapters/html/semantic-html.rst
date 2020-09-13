Semantic HTML
=============

On the previous page, we used a ``<div></div>`` element in the *Try It* section
to center two paragraphs on the screen. This is a very common technique. To
organize content on the page, we often split the page into separate sections.
We can then fiddle with the size, color, alignment, etc. for the elements in
each section without affecting the properties in other parts of the page.

Here's an example of an HTML file that organizes a page into six sections:

.. sourcecode:: html
   :lineno-start: 6

   <body>
      <div>Content...</div>
      <div>
         <div>
            Content...
            <div>
               <img src="..." alt="Text...">
               <div>Content...</div>
            </div>
         </div>
      </div>
      <div>Content...</div>
   </body>

For this short file, we can count the number of opening ``<div>`` tags to
identify the number of sections. However, figuring out what each of the
sections does is more difficult. Maybe the ``<div>`` element on line 13 is a
figure caption for the ``img``? We would need to interpret the content inside
that element, or look at the final page in a browser, before we could say for
sure.

If we wrote the sample code above, we would want to include plenty of comments
in the file to describe the purpose of each ``div`` element. After all, once we
move on to our next project, another programmer might need to update the code
for this page. We must make sure they understand what we created.

.. admonition:: Tip

   Making code work is important, but so is making it easier for others to
   read. Not every piece of code a programmer reads is something they wrote.

Besides comments, recent versions of HTML include a way to use the tags
themselves to describe the layout of a page. The code below builds exactly the
same page as the first example. However, note how it helps answer the question
*What does this section do?*

.. sourcecode:: html
   :lineno-start: 6

   <body>
      <header>Content...</header>
      <section>
         <article>
            Content...
            <figure>
               <img src="..." alt="Text...">
               <figcaption>Content...</figcaption>
            </figure>
         </article>
      </section>
      <footer>Content...</footer>
   </body>

Aha! Finding the figure caption is a snap now, and we can see that we have a
header and footer at the top and bottom of the page. It looks like the purpose
of the ``section`` element is to organize related ``article`` and ``figure``
elements, and the ``article`` tag name gives us a clue about the type of
content that begins on line 10.

HTML Writing Style
------------------

.. index:: ! semantic html

Just like any other author, programmers write HTML with different style guides
and ways of thinking. Two different coders can look at the same set of content
and choose different ways to arrange it on the screen. However, both of them
share the same set of HTML tags to use as tools.

**Semantic HTML** is not about the appearance of the web page. Instead, it's
about the specific meaning of the elements. Semantic HTML uses more descriptive
tag names to help identify what each section of the code does. This helps
programmers clarify the structure of a web page.

For example, developers can make a paragraph larger than a heading if they want
to. By looking at the HTML, however, we can still identify what is the
paragraph and what is the heading. The ``<p>`` and ``<h_>`` tags tell us this.
This is the strength of semantic HTML. The tag names express meaning.

Another benefit to semantic HTML is that beginning programmers find it easier
to visualize the results when they can put a specific name to a section of
their code.

A ``<div>`` by Another Name
---------------------------

Open a new tab in your browser and visit one of your favorite websites. Before
you get too distracted, right-click on the page and choose *View Page Source*.
Examine the HTML code used to build the page. Most likely, you will find a
huge number of ``<div>`` tags. If the web page includes a lot of text, you will
find plenty of ``p`` and ``span`` elements as well.

Semantic tag name examples...

Div vs. other names... same functionality, but more informative to readers of
the code.

Some examples of semantic HTML tags are:
``<p>``, ``<h1>``, ``<h2>`` , ``<strong>``, and ``<section>``.

Image of non-semantic vs. semantic page (code and final appearance).

.. admonition:: Try It!

   Lorem ipsum...

Check Your Understanding
------------------------

Lorem ipsum...
