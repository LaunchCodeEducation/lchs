Cookies
=======

At some point, we've all received an alert in our browser that says something
like, *This website uses cookies*. We hear about cookies all the time, but many
users don't think about them too deeply. They either choose *Accept* or
*Decline* when they see the alert, and then they move on to the next task.

To help us make our Flask applications more efficient, we'll start by taking a
closer look at cookies.

Cookie Ingredients
------------------

.. index:: ! cookie

A **cookie** is just a text file that stores data. Browsers use cookies to help
users navigate a specific website. For example, a cookie can store a user's zip
code, which helps a shopping app find the closest store.

By design, cookies are very small (< 4 kB). Each one consists of a single
key/value pair, like ``zip_code = 63108``. As we surf the web, the browser
stores cookies on our device, usually in the same directory as our browser.

Since the file size is so small, a single website often stores many cookies on
our machine.

.. admonition:: Note

   A deep dive into cookie syntax is beyond the scope of this text. However,
   if you are curious, here are some good resources to get you started:

   #. `All About Cookies <https://www.allaboutcookies.org/faqs/cookie-file.html>`__
   #. `How Stuff Works <https://computer.howstuffworks.com/cookie1.htm>`__
   #. `Cookie playlist from Udacity <https://www.youtube.com/playlist?list=PLs5n5nYB22fLqBWEGW0dBh_yIHdzYlpEz>`__
   #. `HTTP Cookies <https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies>`__
      on the MDN website.

Cookie data is temporary. However, it usually *persists* longer than the values
we assign to Python variables. Cookies often survive after we refresh a page or
exit out of our browser.

.. admonition:: Tip

   We can use the browser preferences to control how long cookies remain saved
   on our device. We can also remove cookies at any time.

   For example, in Firefox we can check our cookie settings by selecting the
   *Privacy & Security* option under *Preferences*. Other browsers provide
   similar features.

   .. figure:: figures/cookie-settings.png
      :alt: Browsers let users manage how cookies are stored on their device.

      We can customize how our browser deals with cookies. We can also clear the data right now.

How Cookies Work
----------------

One thing we need to remember about cookies is that they are NOT programs. They
just store a small amount of data that web servers can use when we visit a site.
Here's a summary of how the cookie process works:

#. The first time we navigate to a webpage, our browser sends an HTTP request
   (``GET`` or ``POST``) to the server.
#. The server sends back an HTTP response, which contains the HTML code for the
   the page. It also includes a command to store one or more cookies on our
   machine.
#. When our browser communicates with that server again, it sends all of the
   saved cookies with the HTTP request. The server uses this data to help it
   process the request.
#. Cookies created by a specific server can only be sent back to that server.
   Cookies created by other servers will NOT be shared. For example, a cookie
   set by `Trinket <https://trinket.io/>`__ won't be sent to the
   `GitHub <https://github.com/>`__ server.

.. todo:: Add a diagram here to show cookie creation and exchange.

Cookies serve several purposes:

#. To keep us logged into a site.
#. To store data that the server needs to remember during our visit. This might
   include our current score in a game or the contents of our shopping cart.
   For example, when we select *Checkout* to complete an online order, cookies
   identify the items we want to buy.
#. To track and analyze our behavior.
   
   a. Have you received targeted adds while searching the web? Cookie data
      influences what you see!
   b. Watch this `short video clip <https://youtu.be/qMFRRoh6vV8>`__ that
      describes how cookies are used to track your movement on the web.

Check Your Understanding
------------------------

Lorem ipsum...
