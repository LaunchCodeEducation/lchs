Boolean Functions
=================

.. index::
   pair: function; boolean

A function that returns a boolean value is known as a **boolean function**.
One simple example tests if an integer is even or odd.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      def is_int_even(integer):
         if integer % 2 == 0:
            return True
         else:
            return False

      print(is_int_even(4))
      print(is_int_even(7))

   **Console Output**

   ::

      True
      False

.. admonition:: Tip

   Start the names of boolean functions with either ``is`` or ``has``, which
   helps make their purpose more clear. For example, reading ``is_int_even(4)``
   tells us that the function should answer the question, "Is the integer 4
   even?"
   
   This convention is so widely used by programmers that it extends to nearly
   every language.

Let's look at ``is_int_even`` again to see how we can use the power of
``return`` statements to make it even better.

Since ``return`` ends the function, we can leave out the ``else`` clause and
have the same effect. If ``integer`` is even, the return statement in line 3
runs, and the function ends. If ``integer`` is odd, the ``if`` block will be
skipped and the second return statement will execute.

.. sourcecode:: python
   :linenos:

   def is_int_even(integer):
      if integer % 2 == 0:
         return True

      return False

   print(is_int_even(4))
   print(is_int_even(7))

The updated version works exactly the same as the original code. 

Also, notice that the function returns ``True`` when the expression
``integer % 2 == 0`` is ``True``, and the function returns ``False`` when
``integer % 2 == 0`` is ``False``. In this case, the return value is *exactly
the same* as the value of ``integer % 2 == 0```. This means that we can
simplify the function even more by returning the result of the expression!

.. sourcecode:: python
   :linenos:

   def is_int_even(integer):
      return integer % 2 == 0

   print(is_int_even(4))
   print(is_int_even(7))

This version of ``is_int_even`` is better than the first two, not because it is
shorter (shorter isn't always better), but because it is simpler to read. We
don't have to break down the conditional logic to see what is being returned.

Most boolean functions can be written so that they return the value of a
boolean expression, rather than explicitly returning ``true`` or ``false``. 

Try It!
-------

Lorem ipsum...

