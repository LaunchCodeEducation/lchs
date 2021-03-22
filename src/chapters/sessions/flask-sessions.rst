Flask Sessions
==============

Cookies provide a useful way to store data for longer periods of time. However,
we must never forget one critical fact:

   Cookie data is not secure.

As we saw on the previous page, the browser tools allow users to view any
cookies stored on their devices. Not only can users access the cookies, they
can also easily modify them.

For example, let's say we create a Flask application to manage an online store.
If we use a cookie to save the total cost of an order, a dishonest customer
could edit the file and change their bill from ``$125.47`` to ``$1.50``.
Similarly, if a different cookie tracks store credit, the user could easily
bump their total from ``$10.00`` to ``$10,000.00``.

For security, we should *never* use cookies to store sensitive data.

Our next step is to add some more security to the persistent data we save. This
step won't protect sensitive data like passwords, but it gets us a little
closer to where we want to go.

What are Sessions?
------------------

.. index:: ! session

.. index::
   single: Flask; session

A Flask **session** uses cookies to store data on a user's device. However,
unlike plain cookies, a session restricts who can change the file. Users can
view the *session cookie*, but they cannot modify it without permission.

A Flask application uses a secret key to create session cookies. Afterwards,
when the browser sends a session cookie back to the server, Flask checks it for
the correct key. If the cookie cannot be verified (because it uses the wrong
key), the data is ignored.

Set Up Flask Sessions
---------------------

Starting a session...

Try It!
-------

Simple session...

Check Your Understanding
------------------------

Lorem ipsum...
