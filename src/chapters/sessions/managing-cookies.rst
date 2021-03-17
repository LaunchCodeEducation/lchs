Flask Cookies
=============

When a server creates a cookie on our browser, it sets a specific time for that
data to last. If no time is set, then the cookie gets erased when we quit the
browser. Putting our device to sleep or closing the tab does NOT clear cookies!

Recall that Flask runs a server on our machine when we launch an application.
This means we can include some Python code to set and access our own cookies.

Let's see how to do this.

Clone the Repository
--------------------

#. Navigate to this GitHub repository. Use the green ``Code`` button to copy
   the URL for the repo.

   .. todo:: Insert GitHub repo link here (cookie practice)

#. Launch Visual Studio Code and use the *File* menu to open your
   ``local_practice`` folder.
#. In the terminal, clone the GitHub repository to your device.

   .. sourcecode:: bash

      $ git clone url_of_repo

   Remember to replace ``url_of_repo`` with the web address you copied in step
   1.
#. After cloning, you should see the ``flask_sessions`` directory in the file
   tree.
#. From the *File* menu, open the ``flask_sessions`` folder.

Properly done, you should now have the following files:

.. todo:: Insert cookie-practice starting file tree here.

Set a Cookie
------------

Go ahead and launch ``main.py``, then open the application in a new browser
tab. The program renders the ``index.html`` template, which displays a short
message in addition to a random number.

.. todo:: Insert screenshot here (Bake Me a Cookie heading).

The program also sets a cookie, but we won't see that on the screen. Let's walk
through the code in ``main.py`` to see what's going on.

.. sourcecode:: Python
   :lineno-start: 7

   # Lorem ipsum...

#. Lorem ipsum...

Viewing Cookies
---------------

Browser tools...

Noting what changes when we stop and restart the program, refresh the page, or
close the tab.

Resources
---------

https://overiq.com/flask-101/cookies-in-flask/

https://pythonise.com/series/learning-flask/flask-cookies
