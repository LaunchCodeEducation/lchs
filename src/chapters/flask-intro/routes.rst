Routes
======

.. index:: ! routing

**Routing** manages the flow of data within a network. When a server receives a
request, it needs to know where to send the information and how to handle the
response. Proper routing helps control this process.

In the case of Flask applications, different HTTP requests trigger different
functions in the Python program. Let's take a closer look at how this works
with ``http://127.0.0.1:5000`` and ``@app.route('/')``.

Server IP Address
-----------------

When we launch a Flask application, it starts a server on our machine. This
server gets its own IP address: ``127.0.0.1``, which is actually the address of
our computer.

Network servers listen for HTTP connections on a specific *port*. To keep
things simple as we develop our application, Flask defaults to a port that is
freely available on our machine (``5000`` in this case). Other ports can be
used, but they may require passwords or other security features. For now, we
won't change the default setting.

.. admonition:: Note

   If you need a quick review, we broke down the different parts of a web
   address in the :ref:`HTTP chapter <web-addresses>`.

When we open a tab in our browser and enter the address
``http://127.0.0.1:5000``, we send a ``GET`` request to the Flask server. When
the server receives that request, our program jumps into action. The
``hello()`` function runs and returns a string. The ``return`` statement in the
function is the *response* to the HTTP *request*. Flask sends the response from
its server to our browser. This generates the content we see on the page (e.g.
``Hello, Flask!``).

How does Flask know what data to send back from the server? This is why we
include the ``app.route()`` decorator. The argument inside the parentheses
corresponds to a specific URL. When the sever receives a request with that web
address, it runs the function immediately below the decorator. In our simple
Flask application, this is the ``hello()`` function.

.. admonition:: Note

   We use ``app.route('/')`` in our code instead of
   ``app.route('127.0.0.1:5000')``. The ``/`` symbol is an abbreviation. It
   stands for the address of the server. Even if the IP address for the server
   changes, Flask will automatically use the proper URL.

Paths
-----

As mentioned before, the ``app.route()`` decorator links a specific URL to one
Python function. The best way to see what this means is to do some live coding.

.. admonition:: Try It!

   #. If the ``hello.py`` application is not currently running, launch it again
      from the terminal. Make sure you see the most recent content in your
      browser.

      .. figure:: figures/flask-form.png
         :alt: A page with an h1 heading and a "New Number" button.

   #. In the address bar, change the URL to ``http://127.0.0.1:5000/hello`` and
      tap *Enter*. Note the *Not Found* error that appears. The message
      explains that the URL you entered isn't on the server.

      .. figure:: figures/page-not-found.png
         :alt: Not Found: The URL in the address bar is not recognized by the server.

   #. In ``hello.py``, change the decorator as follows:

      .. sourcecode:: Python
         :lineno-start: 7

         app.route('/hello')

   #. Save the code, then refresh the tab in your browser. Properly done, you
      should once again see the heading and button.

   Let's think about what just happened.

Recall that URLs can include a *path* as part of the address. The path consists
of one or more names separated by ``/``. The URL
``http://127.0.0.1:5000/hello`` includes the IP address for the server AND a
path to follow.

When we entered ``http://127.0.0.1:5000/hello`` in the address bar, we sent a
different ``GET`` request to the server. We still asked for data, but this time
we told the server to look inside a directory called ``hello``.

In the Python code, ``app.route('/')`` tells Flask, *When a GET request comes
for 127.0.0.1:5000, run the hello() function*. However, there is nothing in
the code that recognizes the address ``127.0.0.1:5000/hello``. When the server
receives that request, Flask scans the Python program for a matching decorator.
Since it doesn't find one, it returns the *Not Found* error message.

By changing ``app.route('/')`` to ``app.route('/hello')``, we fixed the
mismatch. However, this came with a cost.

.. admonition:: Try It!

   Return to your browser and enter ``http://127.0.0.1:5000`` in the address
   bar. What happens?

Navigating to ``http://127.0.0.1:5000`` triggers the ``@app.route('/')``
decorator. Unfortunately, we removed that reference when we replaced ``'/'``
with ``'/hello'``.

What if we want our program to respond to more than one URL? We can do this by
adding more *routes* to the Python code.

Add a Second Page
-----------------

Checkout a new branch in the repo...

Two URLs, same function...

Try It! Add a second page with different text...

We can change between pages in our project by changing the URL in the address
bar. Right now, we're doing this manually. However, we will soon learn how to
do this automatically.

Practice!
---------

Add a third page to the Python code. Update the route to check the page.

.. admonition:: Note

   The server and our application are both running locally. Only *we* can see
   our live webpage, since the requests and responses occur on the same
   machine.
