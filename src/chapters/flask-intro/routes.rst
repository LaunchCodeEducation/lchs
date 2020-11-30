Routes
======

Let's take a closer look at what's happening with ``http://127.0.0.1:5000`` and
``@app.route('/')``.

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
function is the *response* to the HTTP *request*. Flask then steps in to send
the response from its server to our browser. This generates the content we see
on the page (e.g. ``Hello, Flask!``).

Note that the server and our application are both running locally. Only *we*
can see our live webpage, since the requests and responses occur on the same
machine.

Pages and Paths
---------------

As mentioned before, the ``app.route()`` decorator links a specific URL to one
function in our Python code. The best way to see what this means is to do some
live coding.

.. admonition:: Try It!

   #. If the application is not currently running, launch it again from the
      terminal. Make sure you see the most recent content in your browser.

      .. figure:: figures/flask-form.png
         :alt: A page with an h1 heading and a "New Number" button.

   #. In the address bar, change the URL to ``http://127.0.0.1:5000/hello`` and
      tap *Enter*. Note the *Not Found* error that appears. The message
      explains that the URL you entered isn't on the server.

      .. figure:: figures/page-not-found.png
         :alt: The URL in the address bar is not recognized by the server.

   #. In ``hello.py``, change the decorator as follows:

      .. sourcecode:: Python
         :lineno-start: 7

         app.route('/hello')

   #. Save the code, then refresh the tab in your browser. Properly done, you
      should once again see the heading and button.

   Let's explore what just happened.

.. index:: ! routing

**Routing** manages the flow of data within a network. ..

In ``hello.py``, change to ``@app.route('/hello')``...

Explain what **routing** means...

Opening a browser and navigating to ``http://127.0.0.1:5000`` triggers the
``@app.route('/')`` decorator. This is the default location (the address with
nothing after the ``5000``).

We can add more pages to our website by adding more *routes*...

Try It! Add a second page with different text...

We can change between pages in our project by changing the URL in the address
bar. Right now, we're doing this manually. However, we will soon learn how to
do this automatically.

Practice!
---------

Add a third page to the Python code. Update the route to check the page.
