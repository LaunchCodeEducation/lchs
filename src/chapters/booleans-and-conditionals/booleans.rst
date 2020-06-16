.. _booleans:

Boolean Values and Boolean Expressions
======================================

.. index:: data type

One of the key features of any programming language is the ability to decide
whether to run a segment of code. This means you can execute a set of
statements *only if* a given condition is met.

.. admonition:: Example

   Consider an application that reminds you when you have an overdue book. The
   app sends you a message *only if* the due date has passed and you have not
   returned the book.

The *condition* for this example depends on the status of the book. If the
condition is true (overdue), a message gets sent.

In order for us to code this type of decision making, we need to understand how
programming languages represent true and false.

Boolean Values
--------------

.. index:: ! True, ! False, ! boolean ! bool

.. index::
   single: boolean; value

In the previous chapter, you learned about two data types for numbers---``int``
and ``float``. You also considered the ``string`` data type, which deals with
collections of characters. To this, we will add the data type ``bool``, which
stands for **boolean value**.

There are only two boolean values---``True`` and ``False``.

.. admonition:: Note

   Capitalization matters! Since Python is case-sensitive, ``true`` and
   ``false`` are NOT valid boolean values.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      print(True, False)
      print(type(True))
      print(type(False))

   **Console Output**

   ::

      True False
      <class 'bool'>
      <class 'bool'>

The values ``True`` and ``False`` are *not* strings. If you use quotes to
surround booleans (``"True"`` and ``"False"``), those values become strings.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      print(type(True))
      print(type("True"))

   **Console Output**

   ::

      <class 'bool'>
      <class 'str'>

Can We Do Math with Boolean Values?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

We CAN, but we probably SHOULDN'T. Boolean values are used to make decisions,
not solve calculations.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      print(True*5)
      print(False*2)
      print(True + False)
      print(True * False)

   **Console Output**

   ::

      5
      0
      1
      0

What times 5 gives 5? What times 2 gives 0? When we use a mathematical operator
(``+``, ``-``, ``*``, etc.) with boolean values, Python automatically converts
``True`` and ``False`` to the integers ``1`` and ``0``, respectively.

Most of the time, calculations with boolean values are not very useful.
Instead, we use booleans to evaluate *conditions*.

Boolean Expressions
-------------------

.. index::
   single: boolean; expression

.. index::
   single: operator; equality

.. index:: ! ==

A **boolean expression** is one that evaluates to either ``True`` or ``False``.
For example, the **equality operator**, ``==``, compares two values and returns
``True`` or ``False`` depending on whether the values are identical.

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
Line 7 subtracts 3 from the value stored in ``other_num`` and compares the
result with ``num``.

We can also use ``==`` to see that ``True`` and ``"True"`` are NOT equal.

.. admonition:: Example

   .. sourcecode:: python

      print(True == "True")

   **Console Output**

   ::

      False

.. admonition:: Fun Fact

   Boolean values are named after the British mathematician George Boole, who
   created `Boolean Algebra <https://en.wikipedia.org/wiki/Boolean_algebra>`__,
   which is the basis of all modern computer arithmetic.

Comparison Operators
^^^^^^^^^^^^^^^^^^^^

.. index::
   single: operator; comparison

The ``==`` operator is one of six common **comparison operators**.

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
     - ``7 == 7``

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

.. admonition:: Tip

   A common error is using a single equals sign (``=``) instead of a double
   equals (``==``) when comparing two values. Remember that ``=`` is an
   *assignment* operator and ``==`` is a *comparison* operator.

   #. To set or change the value of a variable, use ``=`` (e.g. ``name = 'Mae'``).
   #. To compare values, use ``==`` (e.g. ``name == other_name``).

An equality test is *symmetric*, meaning that we can swap the places of the
operands and get the same the result.  For a variable ``num``, if ``num == 7``
is ``True``, then ``7 == num`` is also ``True``. However, an assignment
statement is NOT symmetric: ``num = 7`` works while ``7 = num`` does not.

Try It!
^^^^^^^

Use the simple code editor below to explore flipping an assignment statement:

.. raw:: HTML

   <iframe src="https://trinket.io/embed/python3/98f98f32c9" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0"></iframe>


Check Your Understanding
------------------------

.. admonition:: Question

   Which of the following are Boolean expressions? Select ALL that apply.

   .. raw:: html

      <ol type="a">
         <li><span id = "a" onclick="highlight('a', true)">3 <= 4</span></li>
         <li><span id = "b" onclick="highlight('b', false)">3 + 4</span></li>
         <li><span id = "c" onclick="highlight('c', true)">"DogCat" == "dog" + "cat"</span></li>
         <li><span id = "d" onclick="highlight('d', false)">"False"</span></li>
         <li><span id = "e" onclick="highlight('e', false)">text = 'Rutabagas!'</span></li>
      </ol>

.. Answers = a and c.

.. raw:: html

   <script type="text/JavaScript">
      function highlight(id, answer) {
         text = document.getElementById(id).innerHTML
         if (text.indexOf('Correct') !== -1 || text.indexOf('Nope') !== -1) {
            return
         }
         if (answer) {
            document.getElementById(id).style.background = 'lightgreen';
            document.getElementById(id).innerHTML = text + ' - Correct!';
         } else {
            document.getElementById(id).innerHTML = text + ' - Nope!';
            document.getElementById(id).style.color = 'red';
         }
      }
   </script>
