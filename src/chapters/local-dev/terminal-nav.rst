Navigating the Terminal Window
==============================

Moving from a GUI to a CLI can be tricky because we are so used to dragging our
files from one folder to another. The first skill we need to practice is how to
figure out where we are in the filesystem!

On the previous page, we used ``pwd`` to print the path to our current
directory. However, we can also find clues inside the terminal prompt:

.. sourcecode:: bash

   Mac
      device_name:directory_name username$

   Windows
      username@device_name MINGW64 path$

``directory_name`` and ``path`` tell us our location in the system. As we enter
commands, ``device_name`` and ``username`` stay the same. However, ``path`` and
``directory_name`` change.

.. admonition:: Note

   In the remaining terminal examples, we will just display the ``$`` symbol
   from the prompt.

Moving Between Directories
--------------------------

We often need to move between directories in the file system. The command
``cd`` (for *change directory*) allows us to do this. The general syntax is:

::

   cd new_directory

``new_directory`` is the path for where we want to be. We do NOT need to
indicate our current location.

.. admonition:: Example

   .. todo:: Insert figure of a file tree with current location marked (``cd`` syntax).

   Let's assume we want to move from our current location in the file tree
   (``dir_name``) to ``other_dir_name``. The terminal command would be:

   .. sourcecode:: bash
      :linenos:

      $ pwd
      current-path
      $ cd absolute-path-to-new-dir
      $ pwd
      new-path

Navigation Shortcuts
^^^^^^^^^^^^^^^^^^^^

When moving through a file tree, we often only need to move up or down one
level. For quick changes like this, we can use a relative path instead of
the absolute one.

.. admonition:: Example

   Let's say we want to move up one level from ``dir_name`` to ``dir_name-1``.
   The terminal shortcut uses ``..``:

   .. sourcecode:: bash
      :linenos:

      $ pwd
      current-path
      $ cd ..
      $ pwd
      new-path

   To move down one level from a parent directory into a subdirectory, the
   path syntax is ``./directory_name``.

   .. sourcecode:: bash
      :linenos:

      $ pwd
      current-path
      $ cd ./directory_name
      $ pwd
      new-path

The ``..`` and ``.`` shortcuts can also be part of a longer path. ``../..``
moves us up two levels from our current directory, while
``./directory_name/other_dir_name`` moves us down two levels.

Feedback
--------

Another big difference between a GUI and a CLI involves the amount of feedback
we receive. With a GUI, we can see when we move, create, or delete a file. The
icon appears, moves, or disappears as we perform the action. Sometimes a window
even pops up to give us more information.

.. figure:: figures/empty-trash.png
   :alt: Dialog box asking if we really want to empty the trash.

   A GUI provides visual feedback.

The terminal rarely displays an output to let us know when a change occurs. We
need to keep an eye on the prompt and be more deliberate about checking the
results of our commands.

Check Your Understanding
------------------------

Navigating file tree questions. Where is the end point for:

- Double up,
- Up, over, and down,
