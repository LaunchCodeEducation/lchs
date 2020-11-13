More Input Attributes
=====================

With the ``input`` element, we have practiced using just a few of the available
attributes: ``type``, ``value``, ``name``, ``id``, ``selected``, and
``disabled``. However, there are many more.

Let's spend some time looking at a few more possibilities. For a complete list
and descriptions of the ``input`` attributes, check out
`W3Schools <https://www.w3schools.com/tags/tag_input.asp>`__.

Placeholder Text
----------------

The ``label`` element for a text input should clearly tell a user what
information needs to go inside the field. An extra hint can be given by
including a ``value`` attribute inside the ``<input>`` tag. This puts some
default text in the field when the page first loads.

One problem with using default text occurs when a user clicks *Submit* without
changing the value in the box. When this happens, the default information is
sent to the server as the user's entry. It would be nice if we could include
some helpful text inside an input box, but prevent that text from getting sent
to the server.

As expected, we can do that! The ``placeholder`` attribute lets us show some
temporary text inside an input field. Once the user starts typing, the
placeholder is immediately replaced by their entry. If the user clicks *Submit*
without typing anything at all, then the empty string is sent to the server.

.. admonition:: Example

   Compare the behavior of the ``value`` and ``placeholder`` attributes inside
   text inputs. Try typing responses into each field.

   .. todo:: Insert interactive Trinket editor here (placeholder attribute).

Resetting a Form
----------------

Reset buttons...

Apply Focus
-----------

Lorem ipsum...

Enable/Disable Input Fields
---------------------------

Plus hidden...

Plus ``checked`` to set a default radio button.
