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

If we code our own modules, like we did in the :ref:`Creating Modules <module-location>`
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

With this picture in mind, it makes a lot of sense to keep the modules we need
in the same directory with the main program.

Import From a Different Directory
---------------------------------

If we create a large number of modules, we might want to add some subfolders to
help keep the files organized. Let's explore this with a simple example.

[FILE TREE - subdirectories]

In this case, ``main.py`` still sits in the ``module_practice`` directory.
However, we moved ``random_list.py`` into the ``helpers`` subfolder.

.. admonition:: Try It!

   #. In VS Code, use the *New Folder* button in the File Explorer to create
      the ``helpers`` directory inside ``module_practice``.
   #. Drag-and-drop the ``random_list.py`` file into the new folder.
   #. Run the program again and examine the error message.

   Lorem ipsum...

When an ``import module_name`` statement runs, Python follows a specific set of
steps to find the required file. We won't detail the entire process here.
However, the short version is:

#. Check if ``module_name`` is one of the standard Python modules. If so,
   import it (the locations of these modules are known).
#. Check the current directory for ``module_name``. If found, import it.

By moving ``random_list.py`` into the ``helpers`` directory, Python can no
longer find the file to import it! This causes the error message.

Fortunately, we can fix the ``import`` syntax and provide a path to where we
stored our module. The key is to include the ``from`` keyword. The general
syntax is:

.. sourcecode:: Python

   from directory_name import module_name

IMPORTANT: ``directory_name`` must be in the same folder as the main program.

.. admonition:: Try It!

   #. In ``main.py``, change line 1 to ``from helpers import random_list``.
   #. Run the program again.
   #. Ta da!

Other Import Details
^^^^^^^^^^^^^^^^^^^^

As long as the modules we need are stored in directories below ``main.py``, we
can go several layers deep with our ``import`` statement. To move down multiple
levels from ``main.py``, we use *dot-notation* and include the different
directory names.

.. admonition:: Example

   [FILE TREE IMAGE - layers deep]

   To import ``my_module``, line 1 in ``main.py`` would be:

   .. sourcecode:: Python

      from sub1.sub2.sub3 import my_module

We can also import a specific function or class from a module stored in a
subdirectory. In this case, we include the module name in our dot-notation.

.. admonition:: Example

   Assume only need the ``average_grades`` function from the ``grade_stats``
   module. The syntax would be:

   .. sourcecode:: Python

      from sub1.grade_stats import average_grades

Importing From a Parent Directory
---------------------------------

While it is possible to force Python so search upwards through your filesystem, 
this isn't recommended. To do so requires a work-around, and that process can
go wrong in lots of ways.

If the Python developers thought it would be useful to search upwards in the
filesystem, then they would have made it easy. They didn't, so it isn't.

Here is a GREAT idea for making local programs and projects: Keep related
content together. This keeps our work organized, and it also helps any other
programmer who might inherit our work.

Whenever you create a custom module to support your program, follow these
guidelines on where to store the file:

#. *Put it in the same directory as the main program*!
#. Put it in a subdirectory below the main program.
#. See point 1.

Check Your Understanding
------------------------

File tree with Q about import path...

Ask about importing from a parent directory...
