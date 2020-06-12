Calling Functions
=================

.. index:: ! method

You have already become familiar with several functions:

- ``print()``
- ``len()``
- Type conversion functions like ``int()``, ``str()``, and ``list()``
- String and list methods, such as ``find()`` or ``reverse()``.

Each of the function works in the same way. By typing the function's name,
followed by parentheses, we *call* the function. This results in an action
being carried out.

Sometimes, we provide data values inside the parentheses. When we do this, the
function carries out its action with that data.

.. admonition:: Example

   The function ``print`` displays the given values in th console.

   .. sourcecode:: python

      print("Hello, World!")

   **Console Output**

   ::

      Hello, World!


[Blank space]








This is an example of a function receiving *input*. Functions may also provide
*output*. For example, the type conversion functions give back the result of
converting a value.

.. admonition:: Example

   Type conversion functions *return* a value, that can be used by the calling code. Often, we store the return value of a function in a variable.

   .. sourcecode:: js
      :linenos:

      let num = Number("42");
      print("The variable num is of type", typeof num, "and has value", num);

   **Console Output**

   ::

      The variable num is of type number and has value 42

.. admonition:: Example

   Many array and string methods also return values. This program uses the string method ``split`` to break a string into separate components.

   .. sourcecode:: js
      :linenos:

      let commaSeparatedValues = "Smith,Jane,100 Cherry Blossom Lane";
      let values = commaSeparatedValues.split(',');
      print(values);

   **Console Output**

   ::

      [ 'Smith', 'Jane', '100 Cherry Blossom Lane' ]

.. index:: encapsulation

Functions are extremely powerful. They allow us to repeat actions without repeating each individual step of code that the actions are built from. By grouping actions together, functions allow us to be removed from the details of what they are actually doing.

When we want to print a message to the console using ``print``, we don't have to know what the console is, or how a string can be displayed on it. The behavior is wrapped up within the function itself. This is an example of a broader programming concept known as **encapsulation**. Encapsulation is the process of packaging up code in a reusable way, without the programmer needing to be concerned with how it works.

.. index::
   single: function; machine

.. _function-machine:

A commonly-used analogy for describing the concept of a function is that of a machine that takes input, carries out an action, and gives back a result. This is known as the **function machine** analogy.

   [FUNCTION MACHINE FIGURE HERE...]

   The function machine

If we want to use a function, we must provide it with some input. It carries
out an action on that input and returns a result. The action occurs within the
function, or "inside the machine". If we know the purpose of a function, we
simply provide it with input and receive the output. The rest is up to the
machine itself.

.. note::

   You may notice that a function like ``print`` doesn't seem to return
   anything. We will soon learn that *every* function returns a value, regardless
   of whether or not that value is used, or is even useful.

The programming concept of a function is very similar to the concept of a mathematical function. For example, in high school algebra you learned about functions like ``y = 4x + 7``. These functions used a mathematical input (``x``) and carried out a procedure to return a numerical result (``y``).

.. admonition:: Example

   Consider the following mathematical function:

   ::

      f(x) = x² + 4x - 2

   We can *call* the function by giving it a specific *input*:

   ::

      f(3) = 3² + 4*3 - 2 = 9 + 12 - 2 = 19

   The number 19 is the *output*.

Functions also allow us to keep our code DRY, a concept that you learned about
:ref:`when we introduced loops <dry-code>`. If we want to do the same basic
task 17 times across a program, we can reduce code repetition by writing one
function and calling it 17 times.
