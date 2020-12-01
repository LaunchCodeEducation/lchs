HTML Templates
==============

In our first Flask app, we simply returned a string to display on a webpage.
By including HTML tags within the string, we can provide structure for the
content. However, this is inefficient. Even for simple webpages, properly
formatting the strings becomes tedious, and avoiding errors is difficult. Why
reinvent the wheel? We already learned how to create quality webpages using
``.html`` and ``.css`` files.

Adding long, triple-quoted strings to our Python functions really isn't a good
idea. Every page in our website would need its own string. Adding all of these
strings clutters up our code and makes our program harder to debug. A better
approach is to keep the HTML code in a separate file. Instead of returning a
string, each Python function points to a specific ``.html`` file. Flask sends
the file to the browser, which *renders* the webpage we want.

This idea lets us separate the *logic* of our application (Python code) from
the *view* (what the user sees in their browser).

What are Templates?
-------------------

.. index:: ! template
   single: Flask; template

A **template** is an outline or structure that can be used multiple times to
produce slightly different results. For example, think of a simple thank-you
form letter:

.. todo:: Insert form letter figure (template analogy).

With this *template*, we can send out dozens of messages very quickly. Most of
the text stays the same. We just need to fill in the blanks from a list of
names/gifts/words (or write some code to do this for us). The template itself
stays the same, but each message looks slightly different.

Templates allow us to DRY our website. We can use one ``.html`` file to fill in
most of the content that appears on a page. Our Python functions add more
specific details, just like filling in the blanks for our thank-you notes.

Templates with Flask
--------------------

Let's update our project to build a webpage from an HTML template. Part of this
setup involves putting our files in very specific locations. We'll start by
creating a ``templates`` directory.

#. Save and commit your work, then checkout a new branch called
   ``template-practice``.
#. In the File Explorer, use the buttons to create a new directory called
   ``templates``.

   .. todo:: Insert render_template file tree here.

#. If we want to use a ``.html`` file as a template, then we MUST put it inside
   the ``templates`` directory. If we don't, then Flask won't be able to find
   the file when we request it.

Add a Template
^^^^^^^^^^^^^^

Inside the ``templates`` folder, create a new file called
``favorite_form.html``. Paste in this HTML code:

.. sourcecode:: html
   :linenos:

   <!DOCTYPE html>
   <html>
      <head>
         <meta charset="UTF-8">
         <meta name="viewport" content="width=device-width">
         <title>Flask Template</title>
      </head>
      <body>
         <form>
            <h2>A Few Of My Favorite Things</h2>
            <label>Favorite Color: <input type="text" name="color"/></label><br>
            <label>Lucky Number: <input type="number" name="luck-num"/></label><br>
            <label>Favorite Class: <input type="text" name="fav-class"/></label><br>
            <label>Favorite Pixar Movie: <input type="text" name="best-pix"/></label><br>
            <button>Submit</button>
         </form>     
      </body>
   </html>

In the :ref:`Local HTML/CSS section <view-local-html>` we learned how to open
HTML files in the browser. Now, however, we are going to have Flask do that job
for us.

The ``render_template`` Function
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. index::
   single: Flask; render_template

#. Return to the ``hello.py`` program. In order to use the template we just
   created, we need to update the first ``import`` statement:

   .. sourcecode:: Python
      :linenos:

      from flask import Flask, render_template

#. The ``render_template`` function contains the code we need to find a
   specific file and send it to the browser. We do NOT need to know how the
   function actually does this. All we need to remember is the syntax for
   calling it:

   .. sourcecode:: Python

      render_template("name_of_template")

   ``name_of_template`` MUST include the extension for the file, like
   ``.html``. Also, the file must be saved inside the ``templates`` directory.

#. Next, add this new function to ``hello.py``:

   .. sourcecode:: Python

      @app.route('/form')
      def form():
         return render_template("favorite_form.html")

#. Save the code, then run the program. Open the browser and navigate to
   ``http://127.0.0.1:5000/form``. Ta da! There's our form.

   .. todo:: Insert screenshot of vanilla form here (flask render result).

``render_template("favorite_form.html")`` locates the HTML file in our project.
``return`` sends this information to Flask, which passes the file to the
browser. Note that the URL in the address bar is NOT the location of the file
on our computer. The template is *on the server*, so its web address reflects
this.

Our form doesn't actually do anything yet, but we'll deal with that on the next
page.

Add Another Template
--------------------

Lorem ipsum...

``render`` vs. ``return redirect``...
