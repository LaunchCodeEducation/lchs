Activity #3: Making Diamonds
============================

One good way to solve large problems is to split them into smaller tasks. With
code, these smaller pieces are solved by writing *functions*. We can then take
the results from each function and combine them to complete the bigger task.

To master functions, you need to write a *lot* of them.

In this activity, you will write lots of small functions and combine their
output. By the end, you will create "shape strings", like this nifty diamond:

.. sourcecode:: bash

       #
      ###
     #####
    #######
   #########
   #########
    #######
     #####
      ###
       #

Part 1: Warm Up (Lines, Rectangles, and Squares)
------------------------------------------------

Review the ``make_line()``, ``make_rectangle()``, and ``make_square()``
functions you wrote for the :ref:`chapter 10 exercises <make-line>`.

These provide a good reminder for how to return a value from a function, how to
use the accumulator pattern, and how to call one function from inside another.

.. admonition:: Examples

   #. Recall that the functions do NOT print anything. Instead, each one
      returns a complete string, which can be assigned to a variable.
   #. Each function definition includes a default parameter for the character
      used to make the shape. If the function call leaves out an argument for
      the symbol, draw the shapes with the ``#`` character.

   .. list-table:: Sample Results
      :header-rows: 1

      * - Function Call
        - Returned Value
        - Printed Output
      * - ``make_line(4, 'a')``
        - ``"aaaa"``
        - aaaa
      * - ``make_rectangle(5, 2)``
        - ``"#####\n#####"``
        - | \#####
          | \#####
      * - ``make_square(3, '$')``
        - ``"$$$\n$$$\n$$$"``
        - | $$$
          | $$$
          | $$$

   Note how the returned strings make use of the *newline character* (``\n``).

Part 2: Making Triangles
------------------------

Lorem ipsum...

Part 3: Make a Diamond
----------------------

Lorem ipsum...
