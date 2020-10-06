How to Do Stuff in the Terminal
===============================

There are many commands you can use in the terminal to move through the
filesystem of your computer and projects.

The list below shows some of the common actions we will take in the terminal:

.. list-table:: Basic Terminal Commands
   :header-rows: 1

   + - Command
     - Result
   + - ``ls``
     - Lists all files and folders in the current directory.
   + - ``cd new_directory``
     - ``cd`` stands for *change directory*. Navigates from the current
       directory to ``new-directory``.
   + - ``pwd``
     - *Print working directory*. Prints the path of the current directory.
   + - ``mkdir new_folder``
     - *Make directory*. Creates ``new_folder`` inside the current directory.
   + - ``touch new_filename``
     - Creates a file called ``new_filename`` in the current directory.
   + - ``rm file_name``
     - *Removes* ``file_name`` from the current directory.
   + - ``man command``
     - *Manual*. Prints to the screen the manual pages for the ``command``.
       This includes the proper syntax and a description of how that command
       works.
   + - ``clear``
     - Empties the terminal window of previous commands and output.
   + - ``cp source_path target_path``
     - *Copies* the file or directory at ``source_path`` and puts it in the
       ``target_path``.
   + - ``mv source_path target_path``
     - *Moves* the file or directory at ``source_path`` from its current
       location to ``target_path``.

.. admonition:: Note

   #. ``rm`` will permanently remove items from the computer and cannot be undone.
   #. Git bash does not support ``man``. Instead, ``<command> --help`` provides a
      scaled down alternative.

Beyond these basic commands, there are some shortcuts if you don't want to type
out the full name of a directory or simply can't remember it.

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

For an in-depth tutorial of how to use a CLI to move through your daily life,
refer to the terminal commands tutorial.

.. todo:: Add a terminal commands tutorial page.
