Exercises: Git More Practice
============================

Working with a Local Repository
-------------------------------

Use your terminal powers to move through these Git exercises.

#. Launch Visual Studio Code and open the terminal pane.
#. In your ``local_practice`` folder, make a new directory called
   ``Git-Exercises``. Next, go to *File --> Open* and select this new folder.
#. In the terminal, make sure that you are in the ``Git-Exercises`` directory.
   Initialize it as a new repository with ``git init``.
#. Add two files to the directory: ``index.html`` and ``style.css``. Use the
   ``status/add/commit`` commands to commit the changes to the repository.
#. Paste in this boilerplate HTML code into ``index.html``, then commit again.

   .. sourcecode:: html
      :linenos:

      <!DOCTYPE html>
      <html>
         <head>
            <meta charset="utf-8">
            <meta name="viewport" content="width=device-width">
            <title>Commit to Git!</title>
            <link href="style.css" rel="stylesheet" type="text/css" />
         </head>
         <body>
            
         </body>
      </html>

#. Use ``git checkout -b`` to create a new branch called ``html-code``. While
   in that branch, add at least 5 new elements to the HTML file. Save and
   commit your changes.
#. Return to ``main``. Use ``checkout`` again to create a third branch called
   ``css-styles``. While in this new branch, open the CSS file and add style
   rules for at least three different elements. Also, include at least one
   :ref:`class selector <css-selectors>`. Save and commit your changes.

You should have 3 branches in your repository now:

::

   $ git branch
   * css-styles
     html-code
     main

Merging
^^^^^^^

Notice that none of the three branches contains a complete set of code.
``main`` and ``html-code`` have a blank ``style.css`` file, while ``main``
and ``css-styles`` do not have the updated HTML. You will fix this with two
merges.

#. Return to ``main`` and use the ``git merge`` command pull in the changes
   from ``html-code``.
#. Check inside ``index.html`` and use ``git log`` in the terminal to confirm
   that ``main`` contains the commits you made in the other branch.
#. Repeat steps 1 and 2 for the ``css-styles`` branch.
#. Can you merge the same two branches again? Find out by moving into the
   ``html-code`` branch and adding more code and commits. Then try merging the
   branch into ``main``. Does it work?

Properly done, at the end of these steps, the ``main`` branch will hold the
complete code for the project. The HTML and CSS branches will only hold parts.

*Bonus*: Try merging ``main`` into the ``css-styles`` branch. Is this
allowed?

.. admonition:: Tip

   Remember that you can view your webpage by
   :ref:`opening the local HTML file <view-local-html>` in your browser.

Merge Conflicts
^^^^^^^^^^^^^^^

The best way to learn how to deal with merge conflicts is to solve merge
conflicts! Avoiding them is preferred, but some will sneak in anyway.

Right now, the ``main`` and ``css-styles`` branches have the same code in the
``style.css`` file. Time to bring in some conflicts...

#. Return to ``main``. Open the CSS file and make the following changes:

   a. In one of your existing element selectors, change the ``color`` property
      for the text.
   b. Add another class selector and assign it some property values.
   c. Add an :ref:`id selector <css-selectors>` and assign it some property
      values.

#. Save and commit your changes.
#. Move into the ``css-styles`` branch and make the following changes:

   a. In the SAME element selector you changed in ``main``, choose a
      different ``color`` for the text.
   b. Add another class selector. Give it the same name as in ``main``. For
      the properties, keep the first one the same but change the other(s).
   c. Add an :ref:`id selector <css-selectors>` and assign it some property
      values. Give this selector a different name than the one defined in
      ``main``.

#. Save and commit your changes.
#. Return to ``main`` and try merging in the ``css-styles`` branch. Spoiler
   alert! There will be some merge conflicts.

As you resolve the conflicts, consider the following:

#. Which changes from parts a - c resulted in conflicts?
#. For which conflict would the option to ``Accept Both Changes`` be a good
   choice?
#. When does changing the same file in two different branches result in a
   conflict?

Don't forget to commit again!

Set up a Github Account
-----------------------

The chapter project and :ref:`Assignment #5 <communication-log>` both involve
using `GitHub <https://github.com/>`__.

Before you attempt these two tasks, check with your teacher for permission to
create a free account. Depending on your school and your course, you might use
a different service to create and share remote repositories.

If you will be using GitHub, create your account by following these steps:

#. Navigate to GitHub's site using the link above.
#. Sign up for an account on the homepage either by filling out the form or
   clicking the *Sign Up* button.
#. Once you have an account, you are ready to store your remote work!
