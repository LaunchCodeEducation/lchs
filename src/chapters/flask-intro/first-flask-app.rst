Your First Flask App
====================

A Flask application is just a Python program. However, we need to organize our
code in a very specific way, and we need to learn some new syntax.

Initial Code
------------

In the ``hello_flask`` directory, create a new Python file called ``hello.py``.
Next, paste this code into the file, then save. We'll discuss what each line
does in a moment.

.. sourcecode:: Python
   :linenos:

   from flask import Flask

   app = Flask(__name__)
   app.config['DEBUG'] = True

   @app.route('/')
   def index():
      text = "Hello, Flask!"
      return text

   if __name__ == '__main__':
      app.run()

**Code explanation**:

#. Line 1: This imports the ``Flask`` class from the module.
#. Line 3: A lot of work goes on behind the scenes when this statement runs. It
   creates an object called ``app`` from the ``Flask`` class. The ``__name__``
   argument contains data that tells Flask where to look for any modules or
   other custom files needed by the program.
#. Line 4: Lorem ipsum...
#. Lines 6 - 9: Lorem ipsum...
#. Lines 11 - 12: This checks to make sure the Python file is being run as the
   main program instead instead of a module. If the condition is ``True``, then
   ``app.run()`` executes and starts the application.

Launch the App
--------------

Lorem ipsum...

Activate Flask ---> run Python program (start server) ---> open port in the
browser.

Try changing the Python code. Refresh the page vs. stopping/restarting the
server. Explain what's going on.

Add random number to the output displayed on the page.

Routes
^^^^^^

Add a second page with different text.

Add Some HTML
-------------

Replace simple text with HTML enclosed in quotes. Note that this renders as
normal HTML on the page!

Render first simple form: Use a button as only element inside a form. Pushing
the button just changes the random number, since all it does is refreshes the
page.

Try It!
-------

Add a third page to the Python code. Update the route to check the page.
