Local HTML/CSS Files
====================

Visual Studio Code recognizes many different programming languages. We can use
the application for our Python projects and our HTML/CSS work.

Let's build a simple webpage just like we did in the :ref:`HTML <html-chapter>`
and :ref:`CSS <css-index>` chapters. However, this time we will do it locally.

Hello, Web
----------

Add a new directory to ``local_practice`` called ``hello_web``. Next, create
two files in the directory called ``index.html`` and ``style.css``.

Our file tree should look something like this:

.. figure:: figures/html-file-tree.png
   :alt: File tree for the hello_web directory. It contains the index.html and style.css files.

   The ``hello_web`` directory tree.

Notice that VS Code displays different symbols next to the files. It uses the
``.html`` and ``.css`` extensions to identify the programming language they
contain.

Paste this code into ``index.html``:

.. sourcecode:: html
   :linenos:

   <!DOCTYPE html>
   <html>
      <head>
         <meta charset="utf-8">
         <meta name="viewport" content="width=device-width">
         <title>Hello, Web!</title>

      </head>
      <body>
         <h1>Hello, Local Webpage!</h1>
      </body>
   </html>

Even though the code only contains a single ``h1`` element, it is still a fully
functional HTML file. Let's see what it looks like in a browser!

Viewing Local Files in a Browser
--------------------------------

There are two ways to view our local HTML file in a browser.

#. Open a web browser. Click on *File --> Open File* from the menu options. In
   the box that pops up, navigate to the ``.html`` file we want. Click *Open*.

   .. figure:: figures/open-html-file.png
      :alt: File menu and dialog box for opening a local file in a browser.

#. Option 2...

Make a change...

Your page can ONLY be seen by you right now...

Adding CSS
----------

Same directory...

Different directory...

Local Project
-------------

Copy/paste your HTML Me Something code into those files.

Open the .html file in a browser.

Live Server package!
