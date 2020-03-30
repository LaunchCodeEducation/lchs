Order of Operations
===================

.. index:: ! order of operations

Consider this example: ``2 + 3 * 4 - 1``. Depending on the order we combine the
numbers, we might get an answer of:

- ``19``
- ``15``
- ``13``
- ``11``

Whenever more than one operator appears in an expression, we must follow a set
of rules to determine the correct answer. These rules are called the **order of
operations**, and they make sure that solving math problems stays the same all
over the world.

Which operators get done first? Here is a summary of the rules for the math
operators, from highest importance (applied first) to lowest (applied last).

.. list-table:: Math Order
   :widths: auto
   :header-rows: 1

   * - Level
     - Category
     - Examples
   * - (Highest)
     - Parentheses: ``()``
     - ``(2 + 3)``
   * - 
     - Exponent: ``**``

       (first value)\ :sup:`second value`
     - ``2**3``
   * -
     - Multiplication and Division: ``*  /  //  %``
     - ``2 * 3``

       ``4 // 2``

       ``15 % 3``
   * - (Lowest)
     - Addition and Subtraction: ``+  -``
     - ``4 - 5``

       ``9 + 1``

If two operators have equal importance, like ``+`` and ``-``, solve them in
order from left to right.

.. admonition:: Example

   The expression ``2 + 3 * 4 - 1`` will be completed in this order:

   #. 3 * 4 is calculated first, since ``*`` has a higher importance than ``+``
      and ``-``.
   #. The ``+`` expression is calculated next (``+`` and ``-`` are equal in
      importance, but the ``+`` is further to the left).
   #. Finally, the ``-`` expression is evaluated, giving us the final result.

   Following this one step at a time:

   .. sourcecode:: Python
      :lineno-start: 0

      2 + 3 * 4 - 1  # Evaluate 3 * 4 first.
      2 + 12 - 1     # Evaluate 2 + 12 next.
      14 - 1         # Evaluate 14 - 1 next.
      13             # Final answer.

What if we wanted to evaluate the ``+`` and ``-`` before the ``*``? To make
this happen, use parentheses: ``(2 + 3) * (4 - 1)``.

.. sourcecode:: Python
   :lineno-start: 0

      (2 + 3) * (4 - 1)    # Evaluate (2 + 3) first.
      5 * (4 - 1)          # Evaluate 4 - 1 next.
      5 * 3                # Evaluate 5 * 3 next.
      15                   # Final answer.

Don't Panic
-----------

.. figure:: figures/scream-emoji.png
   :scale: 80%
   :alt: Don't panic! This is NOT a math class!

OK. Read this section title again.

Python automatically applies the order of operations for you!

However, if you ever notice that your program is not calculating the
answers you expect, you probably have an order of operations issue.

Check Your Understanding
------------------------

OK. These are the expected order of operations questions. Deal with it!

.. admonition:: Question

   What is the value for the following expression?

   .. sourcecode:: Python

      5 - 2 * 6 / 3 + 1

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> 9</li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> 7</li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, true)"> 2</li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> 0</li>
      </ol>
      <p id="Q1"></p>

.. Answer = c (2)

.. admonition:: Question

   What is the output of the code below?

   .. sourcecode:: Python

      print(1 + 5 % 3)

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> 0</li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> 1</li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> 2</li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, true)"> 3</li>
      </ol>
      <p id="Q2"></p>

.. Answer = d (3)

.. raw:: html

   <script type="text/JavaScript">
      function evaluateMC(id, correct) {
         if (correct) {
            document.getElementById(id).innerHTML = 'Yep!';
            document.getElementById(id).style.color = 'blue';
         } else {
            document.getElementById(id).innerHTML = 'Nope!';
            document.getElementById(id).style.color = 'red';
         }
      }
   </script>