Boolean Functions
=================

.. index::
   pair: function; boolean

A function that returns a boolean value is known as a **boolean function**. Perhaps the simplest such function is one that tests an integer to determine if it is even.

.. admonition:: Example

   .. sourcecode:: js
      :linenos:

      function isEven(n) {
         if (n % 2 === 0) {
            return true;
         } else {
            return false;
         }
      }

      console.log(isEven(4));
      console.log(isEven(7));

   **Console Output**

   ::

      true
      false

It is conventional to name boolean functions by starting with either ``is`` or ``has``, which creates a nice semantic effect when reading the code. For example, reading ``isEven(4)`` communicates to the reader that the function should answer the question, "Is 4 even?" This is a convention so widely used by programmers that it extends to nearly every language. 

Let's return to the ``isEven`` function above, to see how we can use the power of return statements to make it even better.

Since ``return`` terminates the function, we can leave out the ``else`` clause and have the same effect. This is because if ``n`` is even, the return statement in the ``if`` block will execute and the function will end. If ``n`` is odd, the ``if`` block will be skipped and the second return statement will execute.

.. sourcecode:: js
   :linenos:

   function isEven(n) {
      if (n % 2 === 0) {
         return true;
      }
      return false;
   }

This updated version works exactly the same as our initial function. 

Additionally, notice that the function returns ``true`` when ``n % 2 === 0`` returns ``true``, and it returns ``false`` when ``n % 2 === 0`` returns ``false``. In other words, the return value is *exactly the same* as the value of ``n % 2 === 0``. This means that we can simplify the function even further by returning the value of this expression.

.. sourcecode:: js
   :linenos:

   function isEven(n) {
      return n % 2 === 0;
   }

This version of ``isEven`` is better than the first two, not because it is shorter (shorter isn't always better), but because it is simpler to read. We don't have to break down the conditional logic to see what is being returned.

Most boolean functions can be written so that they return the value of a boolean expression, rather than explicitly returning ``true`` or ``false``. 
