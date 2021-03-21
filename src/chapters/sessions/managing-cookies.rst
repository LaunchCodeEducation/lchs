Flask Cookies
=============

When a server creates a cookie on our browser, it sets a specific time for that
data to last. If no time is set, then the cookie gets erased when we quit the
browser. Putting our device to sleep or closing the tab does NOT clear cookies!

Recall that Flask runs a server on our machine when we launch an application.
This means we can include some Python code to set and access our own cookies.

Let's see how to do this.

Cookie Video
------------

Watch this short clip to learn how to set cookies with Flask. You can find the
starter code and the end result in this `GitHub repository <https://github.com/LaunchCodeEducation/LCHS_cookie_intro.git>`__.

.. raw:: html

   <section class="vid_box">
      <iframe class="vid" src="https://www.youtube.com/embed/V-jAPj6fETg" frameborder="1" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
   </section>

.. index:: ! make_response, ! set_cookie method

**Video Highlights**:

#. To use Flask to set cookies, stat by importing ``make_response`` from the
   ``flask`` library.
#. The ``make_response()`` function builds the HTTP response sent by the server
   to the browser.
#. In the previous Flask chapters, we sent HTTP responses with
   ``render_template()``. ``make_response()`` lets us do the same thing, but
   it also allows us to set cookies.
#. The argument for ``make_response()`` can be a simple string like
   ``"Hello, World!"``, or it can be the result returned by the
   ``render_template()`` function.

   .. sourcecode:: Python

      make_response("Hello, World!")

      make_response(render_template('template_name.html'))

#. To set cookies, we use the (wait for it...) ``.set_cookie()`` method!
   The general syntax for the method is:

   .. sourcecode:: Python

      response_name.set_cookie(cookie_name, cookie_value)
   
   ``response_name`` is the variable that holds the result from
   ``make_response()``. ``cookie_name`` and ``cookie_value`` must be strings.

#. The ``set_cookie()`` method can take other arguments in addition to the name
   and value for the cookie. However, these go beyond the scope of this course.
   If curious, you can find a more complete description for ``set_cookie()``
   here.

   .. todo:: Insert set_cookie() URL(s).

Viewing Cookies
---------------

As shown in the video, we can use our browser tools to view the cookies saved
for a particular webpage. The specific commands will vary with each browser,
but right-clicking on the webpage is a good thing to try first. Select
*Inspect Element* from the options that pop up, and then open the *Storage*
tab.

[Screenshot of cookie panel]

Note that the cookie data was NOT sent to the webpage as a value. Adding a
{{favorite_cookie}} placeholder to the template results in an unfilled space.
However, the storage panel shows that the cookie file was saved.

Even if we stop the Flask application, the cookie persists in the browser.

[Disconnected screenshot]

When we change the name of the cookie in our Python code and restart the
program, the old cookie file remains. When we load the page again, a new cookie
file is saved.

[Screenshot of updated cookie pane]

Accessing Cookie Data
---------------------

Lorem ipsum...

Resources
---------

https://overiq.com/flask-101/cookies-in-flask/

https://pythonise.com/series/learning-flask/flask-cookies
