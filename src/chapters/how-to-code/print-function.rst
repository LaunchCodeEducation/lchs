The ``print`` Function
======================

In the :ref:`Hello World <hello-world>` section, you practiced displaying text
on the screen. Technically, you sent the words to the **console**, which is a
simple window where the user can type commands or view output. We used the
``print`` function without really talking about how it works.
Let’s fix that now.

We *call* the function using the syntax ``print()``. When the code runs, we
want it to tell the computer, *Please display what is inside the ``()`` on
the screen*. For us, the word ``print`` is simple enough. However, the computer
only understands binary instructions.

When we run the program, Python works behind the scenes to convert ``print()``
into the 0s and 1s that tell the computer *Show this information in the
console*.

.. _print-function:

Examples
---------

Run the example below, and note the difference between the outputs:

.. raw:: html

   <iframe height="500px" width="100%" src="https://repl.it/@launchcode/LCHS-print-statement?lite=true" scrolling="no" frameborder="yes" allowtransparency="true"></iframe>

Observations line by line:

#. In the line 1, we print some text, which is surrounded by quotes.
#. In the line 2, we print a number. Note the absence of quote marks.
#. In line 3, we use three words separated by commas, all within the same
   set of parentheses ``()``. When the words print, they show up on the same
   line separated by spaces.
#. The code in line 4 is just like line 3, only there are no spaces after the
   commas. How does this affect the output?
#. Line 5 prints two words, but in this case the code uses ``+`` instead of a
   comma. This prints the words without spaces in between.
#. Line 6 prints text and a number with a space in between.

Two Special Characters
-----------------------

For all of the examples above, each time we use ``print`` a **newline** is
added after the information. Think of a newline as hitting the *Enter* or
*Return* key on your keyboard. The cursor moves to the beginning of the next
line.

For the computer, *newline* as an invisible character that tells the machine to
move to the next line. We can use this invisible character by adding the
combination ``\n``.

.. admonition:: Try It

   Experiment with the newline character by adding these lines to the editor
   above:

   .. sourcecode:: python
      :lineno-start: 7

      print("Some Programming Languages:")
      print("Python\nJavaScript\nJava\nC#\nSwift")

In addition to the newline character, there is also a special tab character,
``\t``. Go back to the eight examples and play around with using ``\t``
and ``\n``.
