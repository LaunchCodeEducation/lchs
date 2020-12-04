Data Collection
===============

On the previous page, we saw how to use the ``render_template()`` function to
send data from Python to an HTML file. Our next step is to figure out how to
move data in the opposite direction.

For example, when a user clicks *Submit* after filling out a form, they send
data to the web server. The HTTP request contains values for each of the input
fields. As programmers, we need to be able to access this data and work with it
in our Python code.

In our ``hello.py`` program, add the ``request`` object to the ``import``
statement:

.. sourcecode:: Python

   from flask import Flask, render_template, request

We will methods assigned to ``request`` to collect data from a form.


Set ``action`` and ``id`` in form...

Retrieve data, ``print`` result...

``render`` vs. ``return redirect``...
