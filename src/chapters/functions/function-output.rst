Function Output
===============

Now that we have examined arguments and parameters in more detail, let's take a
look at the other end of the function machine---*output*.


.. index:: ! return

When we call a function, we often send one or more arguments *to* that
function. Many functions also send data *back* to the main program. We say
these functions **return** a value.

Return Statements
-----------------

.. index::
   single: return; value

One example of a function that returns a value is ``len()``. When called, the
function takes an argument---like a string or a list---and figures out how many
characters or elements are in the collection. We do not need to know HOW the
``len()`` function works. We just need the result.

``len()`` *returns* the answer we want---the length of the collection. We send
the function an argument (a string or list), and it sends back an integer in
response.

The returned result is the output of the function, and we can picture the
process something like this:

.. todo:: Insert return diagram here (len function)!

   [Caption describing the relationship between argument, parameter, and return
   value.]

Returning a Value
^^^^^^^^^^^^^^^^^

To return a value from functions that we create, we add a **return statement**
to the function body. A return statement has the general syntax:

.. sourcecode:: python

   return some_value

``return`` is the keyword that tells Python, *Send information back to the main
program*. ``some_value`` is the data that needs to be returned, and it may be
any data type (``float``, ``str``, ``bool``, ``list``, etc.).

We may return the value of a variable or the result of an
expression. For example, ``return num`` returns whatever value has been 
assigned to ``num``, while ``return num >= 20`` sends back either ``True`` or
``False``.

.. admonition:: Example

   This function has a single parameter, ``an_int``, which is expected to be
   a positive integer. It returns the sum 1 + 2 + ... + ``an_int``.

   .. sourcecode:: js
      :linenos:

      def sum_one_to_n(an_int):
         total = 0
         for number in range(1, an_int+1):
            total += number

         return total

      result = sum_one_to_n(3)
      print(result)

   **Console Output**

   ::

      6

   Notice that the function ``sum_one_to_n`` contains no ``print`` statements!

Let's take a look at the order of events after we call the function:

#. ``sum_one_to_n(3)`` calls the function and sends it the argument ``3``.
#. Python assigns the argument to the parameter (``an_int = 3``) and then
   runs the function body. ``total`` stores the result from the accumulator
   pattern.
#. Line 6 *returns* the value of ``total`` back to the main program.
#. Line 8 assigns the answer *returned by* the function to the variable
   ``result``.
#. The actual output comes from the final line of the program, which prints the
   value of ``result``.

.. admonition:: Note

   Now that we have ``return`` statements in our coding toolbox, we will very
   rarely print anything from *within* a function. If we want to see the value
   returned by a function, then we must print it AFTER calling the function.

No ``return`` Value
^^^^^^^^^^^^^^^^^^^

Not every function needs to return a value. For example, we can define the
``draw_square`` function for a turtle as follows:

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      import turtle

      def draw_square(turtle_name, side_length):
         for side in range(4):
            turtle_name.forward(side_length)
            turtle_name.left(90)
      
      bob = turtle.Turtle()
      draw_square(bob, 100)

When we call ``draw_square`` in line 9, we do not want the function to give us
an *answer*. Instead, we want it to make a turtle draw a specific shape on the
screen. In this case, there is no need for the function to send any data back
to the main program. Once the turtle finishes moving, the function ends, and
control passes back to the the next statement after the function call.

When we write a function, we must decide whether or not it will return data
once its job is done. We do NOT need to include the ``return`` keyword in
every function.

``return`` Stops a Function
---------------------------

When a ``return`` statement executes, the function ends, even if more code
follows the statement in the function body. This means we must be careful to
use ``return`` only when the work of the function is done.

.. admonition:: Example

   The ``print`` statements in this function never execute, since the function
   returns before either one is reached.

   .. sourcecode:: python
      :linenos:

      def past_the_point_of_return():
         return "I'm done!"
         print("This will NOT be printed!!!!!")
         for line in range(100):
            print("Neither will this!!!!!")

      message = past_the_point_of_return()
      print(message)

   **Console Output**

   ::

      I'm done!

   Written this way, the function behaves as if lines 3 - 5 do not exist!

We can use the fact that ``return`` ends a function to force it to stop at a
specific point.

.. admonition:: Example

   This function adds up the integers 0...n. However, if we send in an argument
   that is NOT a positive integer, the function sends back an error message.

   .. sourcecode:: python
      :linenos:

      def sum_to_n(an_int):
         if type(an_int) != int or an_int <= 0:
            return "Invalid entry. Argument must be a positive integer."
         
         total = 0
         for number in range(an_int+1):
            total += number

         return total
      
      result = sum_to_n('abc')
      print(result)

   **Console Output**

   ::

      Invalid entry. Argument must be a positive integer.

When we call the function in line 11, we send in the string ``'abc'`` as the
argument. On line 6, using a string inside ``range`` would cause the program to
crash, but the ``if`` statement in line 2 prevents that from happening. Since
``type('abc') != int`` is ``True``, the ``return`` statement on line 3
executes and sends the error message back to the main program. In this case,
the ``for`` loop does not run.

Check Your Understanding
------------------------

.. admonition:: Question

   What does the following code output?

   .. sourcecode:: python
      :linenos:

      def plus_two(a_number):
         return a_number + 2

      total = 2

      for turn in range(4):
         total = plus_two(total)

      print(total)

   #. 4
   #. 6
   #. 8
   #. 10

.. Answer = d

.. admonition:: Question

   What does the following function *return*?

   .. sourcecode:: python
      :linenos:

      def say_hello(user_input = 'World'):
         if type(user_input) != str:
            return "Invalid entry."
            
         return "Hello, {0}!".format(user_input)
      
      message = say_hello(5)

   #. ``Hello, World!``
   #. ``Hello, 5!``
   #. ``Invalid entry.``
   #. Nothing (no ``print`` statement)

.. Answer = c.

.. admonition:: Question

   Which of the following functions should include a ``return`` statement?
   Select ALL that apply.

   #. ``calculate_area``
   #. ``draw_polygon``
   #. ``print_names``
   #. ``find_average_score``
   #. ``change_screen_color``
   #. ``create_sorted_string``

.. Answers = a, d, f.

