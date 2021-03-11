Cookies
=======

At some point, we've all received an alert in our browser that says something
like, *This website uses cookies*. We hear about cookies all the time, but many
users don't think about them too deeply. They either choose *Accept* or
*Decline* when they see the alert, and then they move on to the next task.

Cookie Ingredients
------------------

.. index:: ! cookie

A **cookie** is a piece of temporary data stored *in the user’s browser*. By
design, cookies are very small. Each one consists of a single key/value pair,
but browsers often store many cookies from the same website.

Since the data is stored in the browser, users can control how long it remains
saved. They can also remove cookies at any time using their browser tools.

.. admonition:: Examples

   Lorem ipsum...

   ``username = PythonNinja`` Every page in website now says,
   "Hello, PythonNinja!"

How Cookies Work
----------------

Send a GET request to web server. Server sends back data plus a cookie. Every
time the browser communicates with that server, it sends all of the cookies
with its HTTP request. (Does this include cookies for other websites?)

Cookies are unique to a particular server. That is, they only work with the
server that created them. (Confirm this).

Describe the back-and-forth between the user's browser and a web server in
terms of creating and transferring cookies/data...

Web applications use cookies for three main purposes:

#. To keep the user logged into a site, preserve shopping carts, or to store
   data that the server needs to remember during a visit.
#. To keep a record of user preferences, themes, and other settings that
   personalize a website.
#. To track and analyze user behavior.
   
   - Have you received targeted adds while searching the web? Cookie data
     influences what you see!

Viewing Cookies
---------------

Browser tools. Kinda technical screenshot, so maybe skip this...

For More Information
--------------------

A more detailed discussion of cookies is beyond the scope of this book. For
more information, read about `HTTP Cookies <https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies>`__
on the MDN website.
