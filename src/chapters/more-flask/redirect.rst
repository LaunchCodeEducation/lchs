.. _redirect:

Redirecting
===========

.. index:: ! redirect

The term **redirect** means to send a user from one URL to a different one. We
can see a simple example of this with an HTML link element:

.. sourcecode:: html

   <a href="target_URL">Link text</a>

.. admonition:: Example

   The ``target_URL`` for `this link <https://www.python.org/>`__ is
   ``https://www.python.org/``.

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

      <form action="URL_of_server" method="POST">
         <!-- Form code -->
      </form>

   When the user clicks the *Submit* button, an HTTP request is sent to the URL
   assigned to ``action``. This address doesn't have to be the same as the form
   page.
   
   When the server responds to the request, the browser renders a webpage, and
   the new URL appears in the address bar.

Render Template vs. Redirect
----------------------------

Up until now, we've used the ``render_template()`` function to send an HTML
file from the Flask server to the browser. Once the page renders, the URL in
the address bar looks something like ``http://127.0.0.1:5000/path``. For each
page in our website, ``path`` is different.

It is important to recognize that the ``render_template()`` function is NOT the
same thing as a redirect. The best way to see this is with an example.

.. admonition:: Try It!

   In the practice website we've built for this chapter, we currently have
   three pages. Let's use the second and third for this example.

   #. Open ``second.html`` and add a short form after the ``h2``:

      .. sourcecode:: html
         :lineno-start: 5

         <section class="centered">
            <form action="/second" method="POST">
               <h3>Move to the third page?</h3>
               <label><input type="radio" name="choice" value="yes"/>Yes</label>
               <label><input type="radio" name="choice" value="no"/>No</label>
               <section class="centered">
                     <button>Submit</button>
               </section>
            </form>
         </section>
   
      The new form asks the user if they want to move to the third page. The
      ``action`` attribute sends the response to the current URL.
   #. Now open ``main.py`` and update the function that controls the second
      page:

      .. sourcecode:: python
         :lineno-start: 25

         @app.route('/second', methods=['GET', 'POST'])
         def second_page():
            tab_title = "Second Page"
            page_title = "Second Page"

            if request.method == 'POST':
               choice = request.form['choice']
               if choice == 'yes':
                  return render_template('third.html', tab_title = tab_title,
                     page_title = page_title, navigation = navigation)
               else:
                  page_title = "Welcome Back!"

            return render_template('second.html', tab_title = tab_title,
               page_title = page_title, navigation = navigation)

   If the user responds ``No`` in the form, line 36 executes, followed by the
   ``render_template()`` function on line 38. The second page reloads, but it
   shows different text in the heading. (TRY IT!)
   
   If the user responds ``Yes`` in the form, line 33 executes. It renders the
   template for the third page. (TRY IT!)

Responding ``No`` in the form keeps us on the second page. Even though some of
the content changes, we are still rendering the ``second.html`` template.

   [INSERT IMAGE HERE...]

However, notice what happens to the webpage after a ``Yes`` response. The web
address stays the same (``http://127.0.0.1:5000/second``), but the page itself
is different. The URL and heading still indicate the second page, but the
content displayed is for the third.

   [INSERT IMAGE HERE...]

As written, the Python code renders one of two possible templates for the same
URL. *This is NOT a good result*! To keep our website organized, each Python
function should always render the same template. ``second_page()`` should only
deal with ``second.html``.

To properly work with the third page and render ``third.html``, we need to
shift control from ``second_page()`` to a different Python function.

Redirect with Flask
-------------------

Each page in our Flask application has its own template, path, and Python
function. ``render_template()`` should ONLY be used for the HTML file assigned
to the path in ``@app.route()``. If we need to render a different template,
then we should redirect the program flow to a different function.

The general syntax for a redirect in Flask is:

.. sourcecode:: python

   return redirect('/path_name')

``/path_name`` matches the string from one of the other ``@app.route()``
handlers.

Let's update the ``second_page()`` function to use ``redirect()`` instead of
``render_template()``.

.. admonition:: Try It!

   Return to ``main.py`` in Visual Studio Code.

   #. Add the ``redirect`` function to the top ``import`` statement.

      .. sourcecode:: python
         :linenos:

         from flask import Flask, render_template, request, redirect

   #. Inside the ``second_page()`` function, replace the ``render_template()``
      function on line 33 with ``redirect()``.

      .. sourcecode:: python
         :lineno-start: 30

            if request.method == 'POST':
               choice = request.form['choice']
               if choice == 'yes':
                  return redirect('/third')
               else:
                  page_title = "Welcome Back!"

      The string argument inside ``redirect()`` might be different in your
      code. It needs to match the *path* you used in the ``@app.route()``
      statement of the target function.
   #. Save your work, then reload the page in the browser.
   #. Use the form on the second page to answer ``Yes``. After submitting,
      check the URL, heading text, and other content on the page.

   Ta da! We're now properly on the third page!

Notice that besides the path, we didn't include any other arguments inside
``redirect()``. Since it shifts control to a different function, that new
section of code becomes responsible for rendering its own template.

``redirect()`` does NOT directly send any data to the browser. Instead, it
moves control between functions within ``main.py``. 

Difference Summary
------------------

The ``render_template()`` and ``redirect()`` functions Do. Different. Things.

``render_template()``:

#. Deals with displaying a webpage at the current URL.
#. Indicates which file the Flask server sends to the browser.
#. Passes data to the selected template file.
#. The browser renders the file at the path specified in ``@app.route()``.

``redirect()``:

#. Deals with how to move the user from one URL to another.
#. Takes a path argument instead of a file name.
#. Shifts control from one Python function to another.
#. Sends no data directly to the browser.

If ``render_template()`` could talk, it would say something like,
*Hey! Look at this cool stuff right here*. On the other hand, ``redirect()``
would say something like, *Hey! Go somewhere else now*.

Redirect Codes
--------------

In the :ref:`HTTP chapter <http-requests>`, we learned about GET and POST
requests. In the :ref:`Forms chapter <send-data-to-server>`, we learned how to
send each type of request using the ``method`` attribute.

The form on the second page sends a ``POST`` request to the path ``/second``.
However, what happens when the ``redirect()`` statement executes? Does it send
a ``GET`` or ``POST`` request? Let's find out!

.. admonition:: Try It!

   In VS Code, open the template for the third webpage.

   #. Add a new element and placeholder to the template.

      .. sourcecode:: html
         :linenos:

         {% extends "base.html" %}

         {% block content %}
         <h2>Look! A third page!</h2>
         <h3>{{method_message}}</h3>
         {% endblock %}

      We will fill the ``{{method_message}}`` placeholder with different text
      depending on whether we make a ``GET`` or ``POST`` request to reach the
      page.
   #. In ``main.py``, update the function that renders the template for the
      third page. Note that the names you used for the path, function, and
      template might be different than the ones shown.

      .. sourcecode:: python
         :lineno-start: 41

         @app.route('/third', methods=['GET', 'POST'])
         def third_page():
            if request.method == 'POST':
               method_message = 'You reached this page through a POST request.'
            else:
               method_message = 'You reached this page through a GET request.'

            tab_title = 'Third Page'
            page_title = "Third Page"
            return render_template('third.html', tab_title=tab_title, page_title=page_title,
               navigation=navigation, method_message=method_message)

   Add GET/POST check to ``third_page()`` function. Display different text on
   the page depending on the method used.

   Redirect from ``second_page()``, show that the content matches the GET
   condition. Repeat by typing the URL into the address bar or clicking on the
   PN link.

If we want to preserve the POST request to the new URL, we need to add an
argument to the ``redirect()`` function.

Note the 302 code in the POST request above. This has a meaning (link), but we
don't actually need to worry about it. We just need to know the alternative!

In the Try It code above, replace line X with
``return redirect('/third', code=307)``. Again, we don't need to know the
exact meaning behind 307. We just need to know that it preserves the original
method. If redirect is hit via a POST request, it sends its own POST. If it
is hit through a GET request, then it sends its own GET.

TRY IT: Modify code, then visit third page via link, address bar, and form.
Note the difference in the content displayed.

Trace the path of each request sent to the server for the second webpage.

#. Initial load (from PN link or address bar):
   127.0.0.1 - - [22/Jan/2021 15:44:05] "GET /second HTTP/1.1" 200 -
#. After "No" answer:
   127.0.0.1 - - [22/Jan/2021 15:44:25] "POST /second HTTP/1.1" 200 -

   Can see the POST record, and the request for /second.
#. After "Yes" answer:
   127.0.0.1 - - [22/Jan/2021 15:44:54] "POST /second HTTP/1.1" 302 -

   127.0.0.1 - - [22/Jan/2021 15:44:54] "GET /third HTTP/1.1" 200 -

   Flow: Yes is submitted, POST request is sent to /second. Redirect executes,
   and a GET request is sent to /third.

From these console statements, we see that by default, ``redirect()`` sends a
GET request to the new URL. This happens even it the request to the original
URL was a POST.

Send Data with ``redirect``
^^^^^^^^^^^^^^^^^^^^^^^^^^^

``request.method`` works to a limited extent...

Check Your Understanding
------------------------

Lorem ipsum...
