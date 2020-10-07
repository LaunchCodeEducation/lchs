.. _terminal-commands-tutorial:

Terminal Commands Tutorial
==========================

As mentioned in the Terminal chapter, a *command line interface* (CLI) just
uses text. This is quite different from how we usually use our computers and
phones. This tutorial is meant to help you picture how your machine responds
when you enter some common commands.

.. admonition:: Note

   For the purposes of this tutorial, we will use ``current_directory$`` as the
   terminal prompt.

   We will also use this file tree for the examples:

   .. figure:: ../../chapters/local-dev/figures/laptop-file-tree.png
      :alt: File tree for terminal tutorial exercises.
      :width: 80%

.. _terminal_cd:

``cd`` Command
--------------

``cd directory_path`` moves us to the provided path.

Let's start inside the ``LCHS`` directory.

[INSERT FILE TREE HERE]

   We're in ``LCHS``.

To move up one level into the parent directory, run the following:

.. sourcecode:: bash
   :linenos:

   LCHS$ pwd
   /MyLaptop/School/LCHS
   LCHS$ cd ..
   School$ pwd
   /MyLaptop/School

Great! Now we're inside the ``School`` folder.

To go back down into ``LCHS``, we run ``cd ./LCHS``:

.. sourcecode:: bash
   :linenos:

   School$ pwd
   /MyLaptop/School
   School$ cd ./LCHS
   LCHS$ pwd
   /MyLaptop/School/LCHS

OK, we've returned to where we started.

What if we want move to ``Chemistry`` from where we are now, in ``LCHS``?
Looking at the file tree again, we see that we must move up one level from
``LCHS`` and then down into the ``Chemistry`` directory.

[INSERT IMAGE]

In order to move to a directory that is contained within the same parent as our
working directory, we need to first go back up into the parent. One way to do
this is with two separate commands:

.. sourcecode:: bash
   :linenos:

   LCHS$ pwd
   /MyLaptop/School/LCHS
   LCHS$ cd ..
   School$ cd ./Chemistry
   Chemistry$ pwd
   /MyLaptop/School/Chemistry

Line 3 moves us up one level into the ``School`` folder. Line 4 moves us from
there down one level into ``Chemistry``.

.. admonition:: Note

   We can also combine more than one navigation step into a single command. In
   the code above, we could replace lines 3 and 4 with ``cd ../Chemistry``.

Here's a visual of what we just accomplished:

[INSERT FIGURE]

   Path to move to a peer directory.

For practice, let's go from our current spot in ``Chemistry``, down into the
``Homework`` folder.

.. sourcecode:: bash
   :linenos:

   Chemistry$ pwd
   /MyLaptop/School/Chemistry
   Chemistry$ cd ..
   School$ pwd
   /MyLaptop/School
   School$ ls
   Chemistry    LCHS
   School$ cd LCHS
   LCHS$ ls
   Homework
   LCHS$ cd Homework
   Homework$ pwd
   /MyLaptop/School/LCHS/Homework

Above, we checked our location in lines 1, 4, and 12 to keep track of where we
were going. If we're really confident, we can complete the move in a single
command:

.. sourcecode:: bash
   :linenos:

   Chemistry$ pwd
   /MyLaptop/School/Chemistry
   Chemistry $ cd ../LCHS/Homework
   Homework$ pwd
   /MyLaptop/School/LCHS/Homework

Are you starting to see how terminal navigation can get you places quickly?

Let's do one more quick move for fun. To go back to ``Chemistry``, all we need
to do is:

.. sourcecode:: bash
   :linenos:

   Homework$ pwd
   /MyLaptop/School/LCHS/Homework
   Homework$ cd ../../Chemistry
   Chemistry$ pwd
   /MyLaptop/School/Chemistry

Notice that the computer does not display anything after a successful ``cd``
command. In the navigation examples above, we used the :ref:`pwd <terminal_pwd>`
and the :ref:`ls <terminal_ls>` commands to check our location and see what
directories were available to us.

Click here to return to the :ref:`Terminal chapter <basic-terminal-commands>`.

.. _terminal_clear:

``clear`` Command
-----------------

``clear`` wipes the terminal window of all text. It gives us a clean screen
whenever we need a fresh start.

``clear`` doesn't change our location in the file tree.

We usually don't *need* to clear our terminal, but it's a nice command to know
for those who like to avoid clutter. As soon as we hit *Enter* after the
command, the window looks as good as new!

.. sourcecode:: bash
   :linenos:

   LCHS$

Return to the :ref:`Terminal chapter <basic-terminal-commands>`.

.. _terminal_cp:

``cp`` Command
--------------

``cp source_path target_path`` copies the item at the source and puts it in
the target path. The item can be a file or whole directory.

[INSERT IMAGE - Photos location]

Let's say we want to copy our ``cake.jpg`` file and place that copy inside the
``Desktop`` directory.

.. sourcecode:: bash
   :linenos:

   Photos$ ls
   cake.jpg    puppy.jpg   bff.jpg
   Photos$ cp /MyLaptop/Photos/cake.jpg /MyLaptop/Desktop
   Photos$ ls
   cake.jpg    puppy.jpg   bff.jpg
   Photos$ ls ../Desktop/
   cake.jpg

#. Line 1 checks the contents of our current directory.
#. Line 3 copies the ``cake.jpg`` file from its current location
   (``/MyLaptop/Photos``) into a new one (``/MyLaptop/Desktop``).
#. Lines 4 and 6 verify that ``cake.jpg`` now exists in two places on our
   device.

We don't actually need to be in the ``Photos`` directory to copy the
``cake.jpg`` file. We can run the ``cp`` command from any location. However,
starting at the ``source_path`` helps us think through the process.

And of course, now there are two ``lakes.json``.

[INSERT IMAGE HERE]

   ``lakes.json`` double take

We can think of ``cp`` as basically copy *and* paste, since the target path is
included in the command.

Return to the :ref:`Terminal chapter <basic-terminal-commands>`.

.. _terminal_ls:

``ls`` Command
--------------

Lorem ipsum...

Return to the :ref:`Terminal chapter <basic-terminal-commands>`.

.. _terminal_man:

``man`` Command
---------------

Lorem ipsum...

Return to the :ref:`Terminal chapter <basic-terminal-commands>`.

.. _terminal_mkdir:

``mkdir`` Command
-----------------

Lorem ipsum...

Return to the :ref:`Terminal chapter <basic-terminal-commands>`.

.. _terminal_mv:

``mv`` Command
--------------

Lorem ipsum...

Return to the :ref:`Terminal chapter <basic-terminal-commands>`.

.. _terminal_pwd:

``pwd`` Command
---------------

Lorem ipsum...

Return to the :ref:`Terminal chapter <basic-terminal-commands>`.

.. _terminal_rm:

``rm`` Command
--------------

Lorem ipsum...

Return to the :ref:`Terminal chapter <basic-terminal-commands>`.

.. _terminal_touch:

``touch`` Command
-----------------

Lorem ipsum...

Return to the :ref:`Terminal chapter <basic-terminal-commands>`.

.. _terminal-exiting-programs:

Exiting Programs
----------------

.. _terminal-ctrlc:

``ctrl + c`` Details
^^^^^^^^^^^^^^^^^^^^

*ctrl + c* can be used to exit a running program.

Some programs take different commands to exit. *ctrl + c* is sometimes the
command to quit a running program and other times used to prompt the running
program for an different exit command.

.. _terminal-q:

``q``
^^^^^

``q`` is another command for exiting a running program. Notably, it is needed
to exit the :ref:`terminal_man` pages.
