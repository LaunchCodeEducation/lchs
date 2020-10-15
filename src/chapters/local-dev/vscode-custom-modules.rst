Importing Our Own Modules
=========================

On the previous page, we imported the ``turtle`` module into our
``turtle_fun.py`` program. We can do something similar with any of the
ready-made Python modules.

.. sourcecode:: Python
   :linenos:

   import turtle
   import string
   from random import randint

We just need to know the names of the modules we want. We do not need to tell
VS Code where to find those files. Since they are installed with Python, the
application knows where to find them.

If we create our own modules, like we did in the :ref:`Creating Modules <module-location>`
section, then we must be a little more careful with the ``import`` syntax.

Import From the Same Directory
------------------------------

When we create a module, we save the code into its own ``.py`` file. The most
convenient way to import our new module is to put that file in the same
directory as our main program.

[FILE TREE IMAGE]

When we follow this structure, the ``import`` syntax is the same as before.

.. admonition:: Example

   Lorem ipsum...

Think of a large program as a set of smaller tasks joined together. Instead of
writing one large ``main.py`` file with hundreds or thousands of lines of code,
we can split our program into smaller modules. Each one has a specific focus
and purpose. The job of ``main.py`` is to pull them together and manage how
their classes and functions get used.

By splitting our programs into pieces, we make updating and debugging our code
much easier.

With this picture in mind, it makes a lot of sense to keep all of our modules
in the same directory with the main program.

Import From a Different Directory
---------------------------------

If we create a large number of modules, we might want to add some subfolders to
help keep the files organized.

[FILE TREE - subdirectories]

In this case, ``main.py`` still sits in the ``module_practice`` directory.
However, we moved ``random_list.py`` into the ``helpers`` subfolder.

.. admonition:: Try It!

   In VS Code, use the *New Folder* button in the File Explorer to create the
   ``helpers`` directory inside ``module_practice``.

   Drag-and-drop the ``random_list.py`` file into the new folder.

   Run the program again...

Lorem ipsum...

Check Your Understanding
------------------------

File tree with Q about import path...

Lorem ipsum...
