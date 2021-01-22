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
then we must redirect the program flow to a different function.

The general syntax for a redirect in Flask is:

.. sourcecode:: python

   return redirect('/path_name')

``/path_name`` matches the string from one of the other ``@app.route()``
handlers.

Let's update the ``second_page()`` function to use ``redirect()`` instead of
``render_template()``.

.. admonition:: Try It!

   Lorem ipsum...

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
