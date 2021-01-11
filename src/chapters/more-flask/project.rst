Project: Improve the User Experience
====================================

.. index:: ! UI, ! UX

The term **user interface** (UI) refers to the buttons, windows, icons, etc.
that a human interacts with when they use a device.

.. figure:: figures/ui-ux.png
   :alt: Three different user interfaces: a CLI, a GUI, and a smartphone home screen.
   :width: 80%

   Three UI examples: a command line prompt, a clickable file tree, and a touch-sensitive home screen.

**User experience** (UX) refers to the emotions a person feels as they interact
with an application or device. The better developers make the UX, the more
likely people are to keep using their products.

Recall the web form we created in :ref:`the last chapter <server-side-validation>`.
At the time, we noted that if the user enters invalid data, they won't know
about their mistake until they reach the results page. It would be better if we
could return the user to the form page and give them a chance to correct their
entries.

On this page, we will use a fake login form to practice some good UX design.
When a user submits invalid information, we want the following to happen:

#. The form page will reload,
#. A message will appear explaining what went wrong,
#. Valid entries will remain in the input fields,
#. The user can re-enter information and submit again.

Render the Form Again
---------------------

Currently, when we click *Submit* on our form, the ``action`` attribute sends
the data to the ``/results`` route:

.. sourcecode:: HTML
   :lineno-start: 9

   <form action="/results" method="POST">

Display Error Messages
----------------------

Lorem ipsum...

Message flashing: https://flask.palletsprojects.com/en/1.1.x/patterns/flashing/#message-flashing-pattern

Keep Valid Data Intact
----------------------

Lorem ipsum...

Redirect on Success
-------------------

Lorem ipsum...

``render`` vs. ``return redirect``...

Check Your Understanding
------------------------

Lorem ipsum...
