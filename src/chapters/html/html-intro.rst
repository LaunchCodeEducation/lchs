What is HTML?
=============

.. index:: ! hypertext, ! markup language

Indicators of how HTML works are in its name. HTML is short for Hypertext Markup Language.

**Hypertext** is text that includes references to other text known as hyperlinks.

With coding languages, there is a family of languages called **markup languages**. Markup languages annotate the text of a document and define the structure.
HTML is the markup language that defines the structure of hypertext.

HTML's two main components, elements and tags, are key to defining the structure of content.

HTML Elements
-------------

.. index:: ! element

When a programmer creates a web page, they break the content down by type.
They may outline a structure for the page on paper first, highlighting what each item is.
With HTML, a programmer can add a lot of different types of content to a page.
In this chapter, the focus is on headings, paragraphs, images, and more.

An **element** is a segment of an HTML page. Elements are oftentimes broken down by content type.

HTML tags
---------

.. index:: ! tag

An HTML **tag** is the syntax that the computer processes to determine the type and content of an HTML element.

Tags surround the content within the element, so in all cases, programmers need to have opening and closing tags.

Each tag has the following structural elements:

1. ``<`` to start a tag and ``>`` to close it.
2. The type of element it is.
3. Optional additional specification about the element's appearance.
4. Closing tags include the same information as the opening tag with a ``/`` after the ``<`` bracket.

Here is an example of a line of HTML:

::

   <element type>content</element type> 

HTML Writing Style
------------------

Programmers write HTML different ways with different style guides and philosophies.
**Semantic HTML** is not about the appearance of the web page, but about the specific meaning of the elements.
Semantic HTML helps programmers communicate through code and may be easier to pick up at first.
Programmers can make a paragraph larger than a heading.
But by looking at the HTML, another programmer can understand which is the paragraph and which is the heading.
Another benefit to semantic HTML is that it is easier for beginning programmers to visualize the end results.
Some examples of semantic HTML tags are: ``<p>``, ``<h1>``, ``<h2>`` , and ``<div>``.

.. admonition:: Reminder

   Making code work is important and so is making it easier for other programmers to read.
   Not every piece of code a programmer reads is something they wrote.

Check Your Understanding
------------------------

.. admonition:: Question

   What does HTML stand for?

   #. Happy Tickles Make Laughter
   #. Hypertext Markup Language
   #. Hypertext Mockup Language
   #. Hyperlink Markup Layout
