Flask Cookies
=============

When a server creates a cookie on our browser, it sets a specific time for that
data to last. If no time is set, then the cookie gets erased when we quit the
browser. Putting our device to sleep or closing the tab does NOT clear cookies!

Recall that Flask runs a server on our machine when we launch an application.
This means we can include some Python code to set and access our own cookies.

Let's see how to do this.

Setup
-----

#. Navigate to this GitHub repository. Use the green ``Code`` button to copy
   the URL for the repo.

   .. todo:: Insert GitHub repo link here (cookie practice)

#. Launch Visual Studio Code and use the *File* menu to open your
   ``local_practice`` folder.
#. In the terminal, clone the GitHub repository to your device.

   .. sourcecode:: bash

      $ git clone url_of_repo

#. Once completed, you should see the ``flask_sessions`` directory appear in
   the file tree.
#. From the *File* menu, open the ``flask_sessions`` folder.

Properly done, you should now have the following files:

.. todo:: Insert cookie-practice starting file tree here.

Set a Cookie
------------

Go ahead and launch ``main.py``, then open the application in a new browser
tab. All the program does is render the ``index.html`` template, which displays
a short message in addition to a random number.

Lorem ipsum...

https://overiq.com/flask-101/cookies-in-flask/

https://pythonise.com/series/learning-flask/flask-cookies
