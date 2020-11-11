Submitting Forms
================

.. index::
   single: form; submission

Forms collect data from the user. Our first basic web form included two simple
text inputs, one for a ``Username`` and one for a ``Team Name``. We could type
whatever we want into the two fields, but that's it. The form doesn't actually
*send* the information anywhere.

As we learned in the :ref:`HTTP chapter <request-response>`, actions on the web
involve a series of HTTP requests and responses. When we click on a link or
enter a URL in the browser's address bar, we request a specific page stored on
a server somewhere. Data moves from the server to our browser (the client). A
**form submission**, on the other hand, is an HTTP request sent to a server
that contains values collected from a form. In this case, data moves from the
client to the server.

To collect the data entered by a user and send it on its way, we need to
*trigger* the form submission.

Submit a Form
-------------

Form submission is triggered by clicking a button inside the form. This button
often appears with a label like *Submit*, *OK*, or *Login*. Regardless of the
label, we call this a ``submit`` button. We add it to our forms one of two
ways:

#. Using a separate ``input`` element with the ``type="submit"`` attribute.
#. Using a ``button`` element.

Each of these methods is shown in the box below.

.. admonition:: Example

   Here is our basic form again, but this time we added two buttons inside the
   element.

   .. sourcecode:: html
      :lineno-start: 13

      <form>
         <label>Username <input type="text" name="username"/></label><br>
         <label>Team Name <input type="text" name="team"/></label>
         <!-- clicking either of these will cause a form submission -->
         <input type="submit"/>
         <br>
         <button>Login</button>
      </form>

   .. figure:: figures/two-form-buttons.png
      :alt: Form with two text inputs and two buttons ("Submit Query" and "Login")

      Adding two buttons to our basic form.

   Note that the ``<input type="submit"/>`` syntax automatically adds the words
   ``Submit Query`` inside the button. To change the text, we must add the
   ``value="button-text"`` attribute inside the tag and replace ``button-text``
   with the label we want.
   
   The ``<button>`` element has no default value. The text we put between the
   tags appears inside. If we leave this out, an empty button appears with
   the form.

   We only need one button in our form, but we used both here just to see the
   HTML code for each option. Note that without the ``<br>`` element on line
   18, the two buttons would appear side by side.

Try It!
^^^^^^^

#. In Visual Studio Code, open the ``index.html`` file that contains your form.
#. Select one of the button options and add the new element to your HTML code.
   Make the text inside the button say something other than ``Search Query`` or
   ``Login``.
#. Save your work.
#. Open the ``index.html`` file in your browser.
#. Type something into each input field, then click the button. Pay attention
   to what happens inside the address bar of your browser.

Did you catch the change? Try it again, but this time enter ``Bob`` for the
username and ``Python`` for the team.

When you first loaded your form, the URL probably looked something like this:

::

   file:///username/Desktop/local_practice/forms_chapter/index.html

After filling in the input boxes and clicking *Submit*, the address changes to
something like this:

::

   file:///username/Desktop/local_practice/forms_chapter/index.html?username=Bob&team=Python

Let's explore why this happens.

Taking ``action``
-----------------

When a form is submitted, an HTTP request is sent to a server. However, we need
to identify *where* to send the data. To do this, we must include an attribute
inside the ``<form>`` tag, and this attribute is called ``action``.

If the ``action`` attribute is missing or empty, then the form submits all of
the collected data to the URL for the current page. This is why we saw a change
in the address bar after we clicked *Submit*.

.. index::
   single: url; query parameter

The start of the new address matches the old one. However, it also contains
some extra information. The URL now includes a :ref:`query string <query-string>`
after the ``?`` in the address. The query string is made up of separate
**query parameters**, which contain the data collected from each input box in
the form.

For example, the query string ``?username=Bob&team=Python`` contains two
parameters. The first indicates that ``Bob`` was collected from the
``username`` input. The second shows us that ``Python`` was entered in the
``team`` field.

.. admonition:: Note

   Since spaces are not allowed in URLs, the browser replaces them with ``+``.

   Try it! Submit the form again, but type several words into one of the input
   boxes.

Key-value Pairs
^^^^^^^^^^^^^^^

When a form is submitted a key-value pair is created for each named input. The keys
are the values of the ``name`` attributes, and they are paired with the content of the
``value`` attributes.

Form with two named inputs:

.. sourcecode:: html

   <form action="">
      <label>Username <input type="text" name="username"></label>
      <label>Team Name <input type="text" name="team"></label>
      <button>Submit</button>
   </form>

When this form is submitted with the values from the previous example, the query string looks like this:

::

   username=salina&team=Space+Coders

Submitting Passwords
--------------------

Lorem ipsum...

Check Your Understanding
------------------------

.. admonition:: Question

   What must be added to a form to enable submission?

.. admonition:: Question

   By *default*, are HTTP forms submitted with GET or POST?
