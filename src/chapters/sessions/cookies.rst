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
with its HTTP request. However, this only apples to cookies set by the server.
Cookies created by other servers will NOT be sent (e.g. cookie from
www.replit.com won't be sent to www.trinket.io).

   [INSERT DIAGRAM HERE for cookie creation and sending]

HTTP Response: ``Set-Cookie: name = value``. That's it. One cookie, one
key/value pair. HTTP responses can contain multiple set-cookie commands.

HTTP Request: ``Cookie: name=value; name=value; etc.``

Cookies are unique to a particular server. That is, they only work with the
server that created them. (Confirm this).

Describe the back-and-forth between the user's browser and a web server in
terms of creating and transferring cookies/data...

Web applications use cookies for two main purposes:

#. To keep the user logged into a site, preserve shopping carts, or to store
   data that the server needs to remember during a particular visit.
#. To track and analyze user behavior.
   
   - Have you received targeted adds while searching the web? Cookie data
     influences what you see!
   - If you're curious, here's a `short video clip <https://youtu.be/qMFRRoh6vV8>`__
     that describes how cookies are used to track your movement on the web.

Viewing Cookies
---------------

Browser tools. Kinda technical screenshot, so maybe skip this...

For More Information
--------------------

A more detailed discussion of cookies is beyond the scope of this book. For
more information, read about `HTTP Cookies <https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies>`__
on the MDN website.
