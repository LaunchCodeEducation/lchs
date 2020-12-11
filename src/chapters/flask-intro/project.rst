.. _web-caesar-part2:

Project: Web Coded Messages (Part 2)
====================================

In :ref:`Part 1 of this project <web-caesar-part1>`, you designed a form to
collect a text message and two other inputs from the user.

.. figure:: ../forms/figures/caesar-form.png
   :alt: A Caesar Cipher form, with inputs for the original message, the amount to shift, and whether to encrypt or decrypt the text.
   :width: 60%

   One possible form style.

Today, you will move your HTML/CSS code into a Flask application. The goal is
to create a webpage that will encrypt or decrypt the user's message.

Part A: Setup
-------------

Good news! When you cloned the GitHub repository for the Flask
:ref:`chapter exercises <flask-repo>`, you also got access to the starter code
for this project.

.. admonition:: Note

   If you didn't clone the repository, do that now. Return to the exercises
   page and follow the Git instructions in the *Setup* section.

The starter code is located in a different branch in the repository.

#. Open your ``lchs_flask_into`` folder in Visual Studio Code.
#. Save and commit any work you have from the exercises.
#. In the terminal, checkout the project branch:

   ::

      git checkout caesar-project

#. The file tree will change, but don't worry! All your old work is saved in
   your local repository. It's just in a different branch. The new file
   structure looks like this:

   .. figure:: figures/caesar-filetree.png
      :alt: Filetree showing 2 folders and 4 files.

      The ``static`` and ``templates`` directories are ready for your HTML and CSS files.

Pull in Your Part 1 Work
------------------------

You have a couple of different ways of getting the form from Part 1 into your
Flask project.

#. On your device, locate the ``style.css`` file you created for Part 1.
#. To transfer the CSS code to your new project EITHER:

   a. Drag-and-drop your old file into the ``static`` folder. A dialog box
      might pop up and ask if you really want to do this. Agree.

         OR
   
   b. Copy/paste your old code into the empty ``style.css`` file. You now have
      two copies of the same code on your machine. This isn't really DRY, but
      we don't judge (much).

#. Do something similar to get your Part 1 HTML code into the ``user_message``
   file.
#. Once the two files are in place, launch the ``webcaesar.py`` program. Open
   your browser and navigate to the form page.

   a. If you used a different name for your ``.html`` file, update the
      ``render_template()`` function in the Python code.
   b. Remember to use ``url_for`` in your template to link the stylesheet to
      the HTML.

#. When your form renders properly, save and commit your setup.

Part B: Render Form
-------------------

Lorem ipsum...

Collect and Display Message
^^^^^^^^^^^^^^^^^^^^^^^^^^^

Lorem ipsum...

Part C: Encrypt Message
-----------------------

Pull old console code for Assignment 2. Alternatively, find ready-made
encryption code poste on GitHub.

Use request.form to gather message, rotation amount, and encrypt/decrypt
option. Call function, send coded message to webpage for display.

Decrypt Message
^^^^^^^^^^^^^^^

Just call the encryption function and send in a negative shift.

Part D: Validation
------------------

Client-side: Radio button choice, min/max range for number input.

Server-side: Mix/max option for number input (yes, even though the browser
checks as well). Optional max length for message.

Bonus Mission
-------------

Bump up the difficulty of someone breaking the code!

Use keyword in front of alphabet string. Ex: SLIDEabcfghjkmnopqrtuvwxyz.
[Figure showing removal of letters from abc... to build slideabc...]

Will need to add a keyword input field on the form, AND add validation. The
keyword can have no repeated letters.

Will need a new function to build the encoding string.
