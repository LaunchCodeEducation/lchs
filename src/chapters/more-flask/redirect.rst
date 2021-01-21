.. _redirect:

Redirecting
===========

.. index:: ! redirect

The term **redirect** refers to sending a user from one URL to a different one.
We can see a simple example of a redirect with an HTML link element:

.. admonition:: Example

   .. sourcecode:: html

      <a href="target_URL">Link text</a>

   For `this link <https://www.python.org/>`__,
   ``href="https://www.python.org/"``.

Sometimes, clicking a link opens a new tab in the browser. Other times, the new
page loads in the current tab. In both cases, users are sent to a different
URL. This can be confirmed by looking at the address bar before and after the
redirect.

We have also set up redirects with the ``action`` attribute in a form.

.. admonition:: Example

   In the :ref:`Forms chapter <send-data-to-server>`, we sent requests to the
   Response Parrot server.

   .. sourcecode:: html
      :linenos:

      <form action="URL-of-server" method="POST">
         <!-- Form code -->
      </form>

Once the user clicks the *Submit* button, an HTTP request is sent to the URL
assigned to ``action``. This address doesn't have to be the same as the form
page. When the server responds to the request, the browser renders a webpage,
and the new URL appears in the address bar.

Render Template vs. Redirect
----------------------------

Up until now, we've used the ``render_template()`` function to send an HTML
file from the Flask server to the browser. Once the page renders, the URL in
the address bar appears as ``http://127.0.0.1:5000/path``. For each page in our
website, ``path`` is different.

It is important to recognize that the ``render_template()`` function is NOT the
same thing as a redirect. The best way to see this is with an example.

.. admonition:: Try It!

   Demo render template moving to a different page. Note that the web address
   stays the same, but the "page" itself is different. (This isn't a good idea).

   Add a form to the second webpage in chapter examples. Replace "Look! A second
   page!" with a simple form ("Do you want to move to the third page?").
   ``action`` will be back to the second page. After validation, send to third
   page if response is "Yes".

Note that responding "Yes" renders the 3rd page, but look at the address bar!

Note that "No" returns us to the form page (with extra info because of POST).
Same URL in the address bar (/second).

Redirect with Flask
-------------------

Each page in our Flask application has its own template and its own function in
the Python code. ``render_template()`` should ONLY be used for the HTML file
assigned to the path in ``@app.route()``. If we need to render a different
template, then we must *redirect* the program flow to a different function.

To shift control from one Python function to another in a Flask application,
the general syntax is:

.. sourcecode:: python

   return redirect('/path_name')

``/path_name`` matches the string from one of the other ``@app.route()``
handlers.

.. admonition:: Try It!

   Update example to use redirect inside the POST block of the ``second()``
   function.

Redirect Codes
--------------

Redirect codes (GET vs. POST)...

By default, a redirect sends a GET request to the new URL...

Add GET/POST check. Redirect on GET (to prevent users from just entering the
URL in the address bar). We'll learn a more secure way to do this later in the
course. This is a crude way of adding security, and it is far from perfect. We
really need a way of checking if the user is logged in *before the page loads*.

Can send limited data with the redirect, just like with render template...

Wrap-up
-------

Redirect sends users to a different path...

Idea behind redirect: *Go over there now*. Idea behind render template:
*You're in the right spot, now look at this*...

Check Your Understanding
------------------------

Lorem ipsum...
