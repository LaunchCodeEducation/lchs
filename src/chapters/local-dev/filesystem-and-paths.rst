Filesystem and Paths
====================

.. index:: ! filesystem, ! directory, ! subdirectory
   single: directory; root
   single: directory; parent
   single: directory; sub

A **filesystem** on a computer controls how data is stored and retrieved on the
device. One important job of the system is to organize data in a series of
files and folders.

Inside a filesystem, folders are called **directories**. Folders nested inside
other folders are called **subdirectories**. Folders that store others are
called **parent directories**.

.. admonition:: Example

   Most of us have a ``Desktop`` folder on our computers. If there is a folder
   on our Desktop called ``LCHS_Homework``, then the parent directory is
   ``Desktop`` and the subdirectory is ``LCHS_Homework``.

Computer file systems start with one top-level directory that holds everything
else on the machine. This is called the **root directory**. In most cases, the
root directory refers to the primary hard drive. For Windows, that's the
``C drive``. On a Mac, we refer to the root directory with ``/``.

.. index:: ! path
   single: path; absolute
   single: path; relative

A **path** for files and folders is the list of directories that the computer
must follow to find a particular item. This begins with the root directory and
ends with the name of the required item. Think of a path as a set of directions
to get from point A to point B.

.. todo:: Insert screenshot of the path seen in a terminal window.

Filesystems use two different types of paths: *absolute* and *relative*.
The **absolute path** starts at the root directory and ends with the file name.
The **relative path** starts at the current directory and ends with the file
name.

.. admonition:: Example

   Let's assume we have a file inside the ``LCHS_Homework`` directory called
   ``hello.py``. The absolute path would look something like this:

   ::

      Mac:
      /Users/StudentName/Desktop/LCHS_Homework/hello.py

      Windows:
      C:\windows\Desktop\LCHS_Homework\hello.py

   If we are currently in the ``Desktop`` directory, then the relative path for
   ``hello.py`` is:

   ::

      Mac:
      /LCHS_Homework/hello.py

      Windows:
      \LCHS_Homework\hello.py

Many programmers use paths to navigate through the filesystem in the terminal.
We will practice this in the next section.

As we work with the CLI more, paying attention to correct file paths becomes
very important!
