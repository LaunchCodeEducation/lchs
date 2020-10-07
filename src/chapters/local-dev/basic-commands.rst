How to Do Stuff in the Terminal
===============================

There are many commands we can use in the terminal to move through the
filesystem of our computers. The list below shows some of the common actions
programmers take.

Clicking on a link in the table will lead to a tutorial on how to use that
command.

.. todo:: Add a terminal commands tutorial page. Also, add links to it from the commands table.

.. list-table:: Basic Terminal Commands
   :header-rows: 1

   + - Command
     - Result
   + - ``ls``
     - Lists all files and folders in the current directory.
   + - ``cd new_directory_path``
     - ``cd`` stands for *change directory*. Navigates from the current
       directory to ``new_directory``.
   + - ``pwd``
     - *Print working directory*. Prints the path of the current directory.
   + - ``mkdir folder_name``
     - *Make directory*. Creates ``folder_name`` inside the current directory.
   + - ``touch new_filename``
     - Creates a file called ``new_filename`` in the current directory.
   + - ``rm file_name``
     - *Removes* ``file_name`` from the current directory.
   + - ``man command``
     - *Manual*. Prints to the screen the manual pages for the ``command``.
       This includes the proper syntax and a description of how that command
       works.
   + - ``clear``
     - Empties the terminal window of old commands and output.
   + - ``cp source_path target_path``
     - *Copies* the file or directory at ``source_path`` and puts it in the
       ``target_path``.
   + - ``mv source_path target_path``
     - *Moves* the file or directory at ``source_path`` from its current
       location to ``target_path``.

.. admonition:: Note

   #. ``rm`` permanently deletes items from the computer. This action cannot be
      undone.
   #. Git Bash does not support ``man``. Instead, ``command --help`` provides
      a similar result.

Beyond these basic commands, there are some shortcuts we can use in place of
typing out a full path or directory name.

.. list-table:: Directory Shortcuts
   :header-rows: 1
   :widths: auto

   + - Shortcut
     - Where it goes
   + - ``~``
     - The Home directory
   + - ``.``
     - The current directory
   + - ``..``
     - The parent directory of the current directory

.. admonition:: Tip

   If we type the first few letters of a directory name and tap the *Tab* key,
   the terminal will often automatically complete the name for us!

   ::

      $ ls
      homework       really_long_directory_name
      README.md      docs
      $ cd re  <-- Tap the Tab key
      $ cd really_long_directory_name  <-- Presto!

Check Your Understanding
------------------------

.. admonition:: Question

   What line in a CLI indicates that the terminal is ready?

   a. prompt
   b. command
   c. shell
   d. There isn't a line that does that.

.. admonition:: Question

   Which shortcut takes you to the parent directory?

   a. ``.``
   b. ``~``
   c. ``..``
