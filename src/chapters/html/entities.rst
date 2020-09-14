.. _html-entities:

HTML Entities
=============

Some symbols, like ``<`` and ``>`` are reserved for use in HTML code. If we
include reserved characters in the text we want to display on the screen, web
browsers might interpret the symbols as tags.

.. admonition:: Example

   The following HTML code should display a simple paragraph element, followed
   by two (non-working) buttons. Unfortunately, the page does not display
   correctly, and the editor shows several error messages.

   Hover over each red *X* in the editor to read each error message.

   .. todo:: Insert interactive Trinket here (HTML entity examples).

.. index:: ! character entities

**Character entities** are used to display reserved characters in HTML. To
safely display a reserved character on the screen the general syntax is:

.. sourcecode:: HTML

   &entity_name;
   &#entity_number;

In the code editor above, replace the ``<<`` in line X with ``&lt;&lt;`` to
make the *Back* button appear as intended.

Lines Y & Z render properly, but adding ``&lt;`` and ``&gt;`` in place of the
symbols makes the error messages go away.

Each reserved character has its own name, like ``gt`` for the greater than
sign, and a separate number. Besides reserved characters, we can also use
entity names and numbers to display special symbols.

.. todo:: Insert table for selected HTML entities.
