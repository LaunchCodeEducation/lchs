CSS Structure
=============

.. index:: ! inline style

In the HTML chapter we :ref:`added attributes <attributes-example>` to some
elements to control their appearance on the webpage. This is called
**inline styling**, because we assign different property values inside one line
of HTML:

.. sourcecode:: html

   <tag_name style="property:value; property:value; property:value">Content</tag_name>

While this works fine, the syntax becomes tedious when we want to style
multiple elements the same way.

.. admonition:: Example

   Let's say we want every heading on our webpage to show blue text and be
   centered on the page. Using inline styling, the HTML might look something
   like:

   .. sourcecode:: html
      :linenos:

      <body>
         <h1 style="color:blue; text-align:center">Main Page Heading</h1>

         <h2 style="color:blue; text-align:center">Sub-heading #1</h2>
         <!-- Some content -->

         <h2 style="color:blue; text-align:center">Sub-heading #3</h2>
         <!-- More content -->
      </body>

Notice that we include the same ``style="color:blue; text-align:center"``
attribute in each heading tag. We are repeating ourselves!

Fortunately, CSS allows us to DRY our code and reuse the same set of styling
instructions across different elements.

Writing CSS
-----------

.. index:: ! rule, ! selector, ! declaration block

We can set many different style properties using CSS **rules**. A rule includes
a **selector** and a **declaration block**. The *selector* determines which
HTML elements the rule applies to. Inside the *declaration block*, we set CSS
properties to specific values.

The general syntax is:

::

   selector {
      declaration block
   }

CSS includes a lot of different properties, and it would be difficult to
memorize the names for them all. In this chapter, we will use only a few of the
most common.

CSS Selectors
^^^^^^^^^^^^^

.. index::
   single: selector; element
   single: selector; class
   single: selector; id

CSS has three different selectors that we can use to make our style choices.

#. **Element selector**: *Element* refers to an HTML tag name. For example, if
   we use the selector ``p``, then the styling we define applies to all
   paragraph elements on the webpage.
#. **Class selector**: A *class* is a group of different HTML elements (like
   ``p`` and ``section``) that need the same styling. The class name is
   determined by the programmer. Like variable names, a class name should be
   descriptive.
#. **ID selector**: An *id* is a specific identification given to a single
   element in an HTML file. For example, if we want only one paragraph on our
   webpage to be bright pink, then we can assign it an ``id``.

Declaration Blocks
^^^^^^^^^^^^^^^^^^

The declaration block is a series of statements that assign values to a set of
property names. Each line in the block sets one property value, and the block
as a whole defines the style for the selector.

.. admonition:: Examples

   The syntax for a declaration block looks something like this:

   .. sourcecode:: css
      :linenos:

      selector {
         property: value;
         property: value;
         property: value;
      }

   For centered, blue ``h2`` elements, the CSS would be:

   .. sourcecode:: css
      :linenos:

      h2 {
         color: blue;
         text-align: center;
      }

Note that the second example above looks similar to the inline CSS we used at
the start of this page, ``style="color:blue; text-align:center"``. In fact, the
two produce the same result. The difference involves where we put the style
instructions.

Inline styling instructions get placed inside the tags in an HTML file. As we
will see in the next section, we can also put the CSS rules in the ``head``
element or even in a completely separate file.

Every property in CSS has a default value. For example, ``color``, which
controls text color, defaults to ``black``. Therefore, we only need to set a
CSS property if we want to change it from the default setting.

CSS Examples
------------

Here are three different examples of how we can use selectors to make some of
the text on a page pink.

Element Selector
^^^^^^^^^^^^^^^^

This element selector sets the text color for ``<p></p>`` elements:

.. sourcecode:: css
   :linenos:

   p {
      color: pink;
   }

Using the element selector will make all paragraph elements on the page have
pink text.

.. todo:: Insert interactive editor here for a CSS Try It example.

Class Selector
^^^^^^^^^^^^^^

What if we only want a few of the paragraphs on the page to be pink? Also, what
if we want some other elements on the page to have pink text as well?

For these cases, we can define a CSS *class*, like so:

.. sourcecode:: css
   :linenos:

   .pink-text {
      color: pink;
   }

In CSS, the class selector begins with a dot followed by the class name we
chose (``.class-name``).

Unlike the element selector, class styling requires us to add a specific
attribute to an HTML tag. For example, if we wanted one pink paragraph and one
pink heading on our page, the HTML would look something like:

.. sourcecode:: html
   :linenos:

   <body>
      <h1 class="pink-text">Main Page Heading (Pink)</h1>

      <h2>Sub-heading #1 (black text)</h2>

      <p class="pink-text">Some pink words here...</p>
      <p>Some black text here...</p>
   </body>

By giving the elements on lines 2 and 6 the ``class`` attribute, we apply the
``pink-text`` styling rule to both. By leaving ``class="pink-text"`` out of the
other tags, the text in those elements remains the default color (black).

ID Selector
^^^^^^^^^^^

If only one element on the page needs to have pink text, then we can add an
``id`` attribute inside that one tag. For example,
``<p id="pinkParagraph">Content</p>``.

In CSS, we define the id selector like so:

.. sourcecode:: css
   :linenos:

   #pinkParagraph {
      color: pink;
   }

In CSS, the id selector begins with the symbol ``#`` followed by the ``id``
name.

.. admonition:: Fun Fact

   The ``#`` has several names/meanings.

   #. *Number*, as in ``#2 pencil`` (number 2 pencil).
   #. *Pound weight*, as in ``77#`` (77 pounds).
   #. *Pound*, when referencing the button on a telephone keypad.
   #. *Hashtag*, for most appearances after 2006.

Try It!
-------

Lorem ipsum...

Use a pre-configured editor with HTML elements and css file. Students practice
applying element, class, and id selectors...
