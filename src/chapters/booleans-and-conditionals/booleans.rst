Boolean Expressions
===================

.. index::
   single: boolean; expression

.. index::
   single: operator; equality

.. index:: ! ==, ! condition

A **boolean expression** makes a comparison and returns one of the boolean
values, either ``True`` or ``False``.

To make a decision within our code, a boolean expression is used as the
**condition**. A condition is a comparison that can be called correct
(``True``) or incorrect (``False``).

Testing for Equality
--------------------

The **equality operator**, ``==``, compares two values and returns ``True`` or
``False`` depending on whether the values are identical.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      num = 37
      other_num = 40

      print(5 == 5)
      print('abc' == 'def')
      print(num == other_num - 3)

   **Console Output**

   ::

      True
      False
      True

In line 4, the two values are equal, so the expression evaluates to ``True``.
In the line 5, the string ``abc`` is not equal to ``def``, so we get ``False``.
Line 7 compares the result of ``other_num - 3`` with the value stored in
``num``.

.. admonition:: Tip

   A common error is using a single equals sign (``=``) instead of a double
   equals (``==``) when comparing two values. We call ``=`` an
   *assignment* operator, but ``==`` is a *comparison* operator.

   #. To set the value of a variable, use ``=`` (e.g. ``name = 'Mae'``).
   #. To compare values, use ``==`` (e.g. ``name == other_name``).

An equality test is *symmetric*, meaning that we can switch the places of the
two values and get the same the result.  If ``num == 7`` is ``True``, then
``7 == num`` is also ``True``. However, an assignment statement is NOT
symmetric: ``num = 7`` works while ``7 = num`` does not.

Try It!
^^^^^^^

Use the simple code editor below to explore flipping an assignment statement:

.. raw:: HTML

   <iframe src="https://trinket.io/embed/python3/151042b620" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0"></iframe>

Other Comparisons
-----------------

.. index::
   single: operator; comparison

The ``==`` operator is one of six common **comparison operators**.

.. index:: ! operand

.. admonition:: Vocabulary

   The values on either side of an operator are called **operands**.

.. index:: ==, ! !=, ! <, ! >, ! <=, ! >=

.. list-table:: Comparison Operators
   :widths: auto
   :header-rows: 1

   * - Operator
     - Description
     - Examples Returning ``True``
     - Examples Returning ``False``
   * - Equal (``==``)
     - Returns ``True`` if two compared values (operands) are equal, and ``False`` otherwise.
     - ``7 == 3 + 4``

       ``'ab' == 'a'+'b'``

       ``"dog" == "dog"``
     - ``7 == 5``

       ``'dog' == 'cat'``

       ``'cat' == 'Cat'``
   * - Not equal (``!=``)
     - Returns ``True`` if two values (operands) are NOT equal, and ``False`` otherwise.
     - ``7 != 5``

       ``"dog" != "cat"``
     - ``7 != 7``

       ``"dog" != "dog"``
   * - Greater than (``>``)
     - Returns ``True`` if the left-hand value (operand) is greater than the right-hand operand, and ``False`` otherwise.
     - ``7 > 5``

       ``'b' > 'a'``
     - ``7 > 7``

       ``'a' > 'b'``
   * - Less than (``<``)
     - Returns ``True`` if the left-hand operand is less than the right-hand operand, and ``False`` otherwise.
     - ``5 < 7``

       ``'a' < 'b'``
     - ``15 < 15``

       ``'b' < 'a'``
   * - Greater than or equal (``>=``)
     - Returns ``True`` if the left-hand operand is greater than or equal to the right-hand operand, and ``False`` otherwise.
     - ``7 >= 5``

       ``7 >= 7``

       ``'b' >= 'a'``

       ``'b' >= 'b'``
     - ``5 >= 7``

       ``'a' >= 'b'``
   * - Less than or equal (``<=``)
     - Returns ``True`` if the left-hand value is less than or equal to the right-hand value, and ``False`` otherwise.
     - ``5 <= 7``

       ``5 <= 5``

       ``'a' <= 'b'``

       ``'a' <= 'a'``
     - ``7 <= 5``

       ``'b' <= 'a'``

Check Your Understanding
------------------------

.. admonition:: Question

   Which of the following are Boolean expressions? Select ALL that apply.

   #. ``3 <= 4``
   #. ``3 + 4``
   #. ``"DogCat" == "dog" + "cat"``
   #. ``"False"``
   #. ``text = 'Rutabagas!'``

.. Answers = a and c.

.. admonition:: Question

   .. raw:: html

      <script type="text/JavaScript">
         function highlight(id, answer) {
            if (answer) {
               document.getElementById(id).style.background = 'lightgreen';
            }
         }
      </script>

      <p>Which of the following are Boolean expressions? Click ALL that apply.</p>
      <ol type="a">
         <li><span id = "3 <= 4" onclick="highlight('3 <= 4', true)">3 <= 4</span></li>
         <li><span id = "3 + 4" onclick="highlight('3 + 4', false)">3 + 4</span></li>
         <li><span id = "DogCat" onclick="highlight('DogCat', true)">"DogCat" == "dog" + "cat"</span></li>
         <li><span id = "False" onclick="highlight('Rutabagas', false)">"False"</span></li>
         <li><span id = "Rutabagas" onclick="highlight('Rutabagas', false)">text = 'Rutabagas!'</span></li>
      </ol>
