Routes
======

Let's take a closer look at what's happening with ``http://127.0.0.1:5000`` and
``@app.route('/')``.

Reference URL section... Recall what a *port* is...

When we run Flask, we start a *local server* on our machine. This server
operates out of a port...

In the browser, change address to ``http://127.0.0.1:5000/hello``... Note the
*Page Not Found* error.

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
