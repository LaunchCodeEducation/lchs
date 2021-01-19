Project: Improve the User Experience
====================================

Recall the web form we created in :ref:`the last chapter <server-side-validation>`.
As designed, if the user enters invalid data, they won't know about their
mistake until they reach the results page. This flaw in the user interface (UI)
lowers the quality of the user experience (UX).

One common practice is to return a user to the original form page when they
make a mistake. Including a message that explains what went wrong gives the
user a smooth way to correct their entries.

For this project, you will update a fake login page to improve the UI/UX. When
a user submits invalid information, the following should happen:

#. The form page will reload,
#. One or more messages will appear explaining what went wrong,
#. All valid entries will remain in their input fields,
#. The user can re-enter information and submit again.

When the user successfully fills out the form, they will be sent to a different
webpage.

Setup
-----

The starter code for this project is saved in the same
`GitHub repository <https://github.com/LaunchCodeEducation/LCHS_flask_logic>`__
you used for the exercises. However, the project code is in a separate branch.

#. Open the ``LCHS_flask_logic`` directory in Visual Studio Code.
#. In the terminal, switch to the ``project-start`` branch:

   .. sourcecode:: bash
   
      $ git checkout project-start

#. Just like you did for :ref:`the chapter exercises <more-flask-exercises-setup>`,
   create and activate a new virtual environment.
#. Install Flask.
#. Save and commit your work.

Run the Application
^^^^^^^^^^^^^^^^^^^

Launch ``main.py`` and open the application in a new tab in your browser.

The form works... Try entering invalid information though...

Note that the form gets erased and no indication is given about what went
wrong!

The layout and colors are a bit distracting... Just because you CAN apply lots
of color, doesn't mean you SHOULD.

Part of the UI includes the appearance of the page and the placement of the
interactive elements.

Clean Up the View
-----------------

Fix distracting rainbow background...

Update font-size...

Add placeholder text...

Style and center the form and button...

Data Validation
---------------

Lorem ipsum...

Currently, when we click *Submit* on our form, the ``action`` attribute sends
the data to the ``/results`` route:

.. sourcecode:: HTML
   :lineno-start: 9

   <form action="/results" method="POST">

Keep Valid Data Intact
----------------------

Lorem ipsum...

Display Error Messages
----------------------

Lorem ipsum...

Redirect on Success
-------------------

Lorem ipsum...

``render`` vs. ``return redirect``...

What's to stop users from just entering the results page URL in the address
bar? Nothing!

Add GET/POST check. Redirect on GET (to prevent users from just entering the
URL in the address bar). We'll learn a more secure way to do this later in the
course. This is a crude way of adding security, and it is far from perfect. We
really need a way of checking if the user is logged in *before the page loads*.

Bonus Mission
-------------

Lorem ipsum...

Message flashing: https://flask.palletsprojects.com/en/1.1.x/patterns/flashing/#message-flashing-pattern
