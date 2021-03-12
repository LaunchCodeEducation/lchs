Cookies
=======

At some point, we've all received an alert in our browser that says something
like, *This website uses cookies*. We hear about cookies all the time, but many
users don't think about them too deeply. They either choose *Accept* or
*Decline* when they see the alert, and then they move on to the next task.

Cookie Ingredients
------------------

.. index:: ! cookie

A **cookie** is a text file that stores data. Browsers use cookies to help
navigate a specific website. 

By design, cookies are very small (< 4 kB). Each one consists of a single
key/value pair. Cookie files are stored on our personal device, usually in the
same directory as our browser.

Since the file size is so small, the same website often stores many cookies on
our machine.

.. admonition:: Note

   A deep dive into cookie syntax is beyond the scope of this text. However,
   if you are curious, here are some good resources to get you started:

   #. `All About Cookies <https://www.allaboutcookies.org/faqs/cookie-file.html>`__
   #. `How Stuff Works <https://computer.howstuffworks.com/cookie1.htm>`__
   #. `Cookie playlist from Udacity <https://www.youtube.com/playlist?list=PLs5n5nYB22fLqBWEGW0dBh_yIHdzYlpEz>`__


Lorem ipsum...

https://www.kaspersky.com/resource-center/definitions/cookies

https://www.allaboutcookies.org/faqs/cookie-file.html

Cookie data is temporary. However, it usually *persists* longer than the values
we assign to Python variables. Cookies can survive after we refresh a page or
exit out of our browser.

.. admonition:: Tip

   We can use the tools in the browser to control how long cookies remain
   saved on our device. We can also remove cookies at any time.

   .. todo:: Add screenshot of browser cookie tools.

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
