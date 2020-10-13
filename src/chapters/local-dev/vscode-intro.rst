Visual Studio Code
==================

Before we dive into coding our first local program, let's take a moment to get
used to our new code editor.

Open the Visual Studio Code program and take a look around.

Welcome Screen
--------------

The first time we run VSCode, the program displays the Welcome screen to get us
started. Go ahead and click the *Open Folder* option and then select the
*Desktop* directory. (Opening any directory activates the workspace, but for
now we will practice on the Desktop).

.. admonition:: Note

   When we launch VSCode, it tries to open the last project we worked on. If
   this happens now, don't worry. Select *New Window* from the *File* menu to
   bring up the Welcome screen.

.. figure:: figures/vscode-welcome.png
   :alt: The VSCode Welcome screen.
   :width: 80%

   Welcome to Visual Studio Code!

Next, click on the *Terminal* menu and select *New Terminal*.

.. figure:: figures/terminal-menu.png
   :alt: VSCode Terminal menu options.
   :width: 70%

   Open the terminal inside VSCode.

We now have several different panels, buttons, and menus that allow us to edit,
debug, and run our code.

The Workspace
-------------

The workspace in Visual Studio Code consists of three main panels:

.. figure:: figures/labeled-workspace.png
   :alt: VSCode workspace with the terminal, main toolbar, and code editor labeled.
   :width: 80%

   The VSCode workspace.

#. **Terminal Panel**: VSCode allows us to run our terminal application inside
   the workspace. All of the actions we practiced in the
   :ref:`Terminal chapter <terminal-chapter>` will work here.
#. **Toolbar and File Tree**: This panel lets us navigate our file system,
   perform searches, install extensions, update the software, etc.
#. **Editor Panel**: Our code goes here! VSCode recognizes most major
   programming languages.

Terminal Panel
--------------

Let's run a couple of terminal commands just to see where we are:

.. sourcecode:: bash
   :linenos:

   Jims-Air:Desktop jimflores$ pwd
   /Users/jimflores/Desktop
   Jims-Air:Desktop jimflores$ ls
   LCHS Notebook files     Training files

Take a look at the file path returned by ``pwd``. By opening the Desktop folder
from the Welcome screen, VSCode automatically put us in that directory when we
opened the terminal.

The ``ls`` command displays the files and folders currently in ``Desktop``.
Notice how the same items appear in the file tree on the left side of the
workspace.

Now use the terminal to create a new directory in the Desktop:

.. sourcecode:: bash
   :linenos:

   Jims-Air:Desktop jimflores$ mkdir local_practice
   Jims-Air:Desktop jimflores$ ls
   LCHS Notebook files     Training files          local_practice

Check your computer Desktop to see that a ``local_practice`` folder appeared.

When we write our first local Python program, we will use the terminal to run
that code.

Toolbar and File Tree
---------------------

The toolbar on the left side of the workspace contains nine buttons, but we
will only look at three of them right now.

#. **File Explorer**: Clicking on the top icon hides/reveals the file tree for
   the current directory.

   .. figure:: figures/vscode-file-tree.png
      :alt: The file tree for the Desktop directory.

   a. Clicking on the ``>`` symbol next to a folder displays the contents of
      that directory.
   b. The file tree includes buttons for adding new files and folders to the
      current directory.

#. **Settings**: Clicking on the gear icon at the bottom of the toolbar brings
   up options for customizing the workspace. For example, if you don't like the
   default theme (dark background with light text), you can change it!
#. **Extensions**: Search, install, update, or uninstall extensions for VSCode.
   Click on the fifth icon from the top to make sure that extensions for Python
   and HTML/CSS are installed. If not, follow the instructions in the
   :ref:`Setting UP VSCode <vscode-extensions>` appendix to add them.

Add a New File
^^^^^^^^^^^^^^

#. Click on the File Explorer icon to show the file tree.
#. Select the ``local_practice`` directory, which is currently empty.
#. Click on the *New File* button.

   .. figure:: figures/new-file-button.png
      :alt: The New File button appears next to the directory name.

#. Notice that a space opens in the file tree where we can enter a filename.
   Type ``hello.py`` and hit *Enter*.

A ``hello.py`` tab appears in the editor panel. Clicking on any filename in the
Explorer will open that file in the editor.

Editor Panel
------------

This is where we will do most of our work in VSCode.

Let's do some local coding!
