Improve the User Experience (UX)
================================

.. index:: ! UI, ! UX

The term **user interface** (UI) refers to the buttons, windows, icons, etc.
that a human interacts with when they use a device. For the form we've been
using throughout this chapter, the UI includes the four input fields and the
*Submit* button.

.. figure:: figures/ui-ux.png
   :alt: Three different user interfaces: a CLI, a GUI, and a smartphone home screen.

   Three UI examples: a command line prompt, a clickable file tree, and a touch-sensitive home screen.

**User experience** (UX) refers to the emotions a person feels as they interact
with an application or device. The better we make the UX, the more likely
people are to keep using our product.

On this page, we will keep the UI the same (4 fields plus a button). However,
we can do a few things to improve a user's experience with the form. If they
submit invalid information, we want the following to happen:

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
