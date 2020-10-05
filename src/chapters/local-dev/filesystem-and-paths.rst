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

A **path** for files and folders is the list of directories that the computer
must follow to find that particular item. This begins with the root directory
and ends with the name of the required item.

.. index:: ! path
   single: path; absolute
   single: path; relative

Filesystems have two different types of paths: absolute and relative.
The **absolute path** is the path to a file from the root directory.
The **relative path** is the path to a file from the current directory. When working with a relative path, you may find yourself wanting to go up into a parent directory to find a file in a different sub, or child, directory.
In order to do so, you can use ``..`` in the file path to tell the computer to go up to the parent directory.

.. admonition:: Example

   We have a file inside our ``LC101_Homework`` directory from the above example.
   We named that file ``homework.js``.
   The absolute path for ``homework.js`` is ``/Users/LaunchCodeStudent/Desktop/LC101_Homework`` for Mac users and ``C:\windows\Desktop\LC101_Homework`` for Windows users.
   If the current directory is ``Desktop``, then the relative path for ``homework.js`` is ``/LC101_Homework`` for Mac users and ``\LC101_Homework`` for Windows users.

   Say ``homework.js`` is in a different directory called ``CoderGirl_Homework``. ``CoderGirl_Homework`` is inside 
   the ``Desktop`` directory. Your current directory is ``LC101_Homework``. In this scenario, we would use the 
   ``..`` syntax in our relative path. The relative path would then be ``/../CoderGirl_Homework`` for Mac users 
   and ``\..\CoderGirl_Homework`` for Windows users.

Many programmers use paths to navigate through the filesystem in the terminal.
We will discuss the commands to do so in the next section.

