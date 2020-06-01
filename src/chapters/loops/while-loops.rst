``while`` Loops
===============

.. index:: ! while

.. index::
   single: loop; while

There is another Python keyword that can also be used for iteration---``while``.
Unlike a ``for`` loop, which defines a loop variable and a specific starting
and ending point, a **while loop** uses a single condition to determine whether
or not to continue running.

This condition (a boolean expression) controls the iteration. The body of a
``while`` loop repeats as long as the expression evaluates to ``True``.

.. TODO: Add internal link here leading back to the boolean expressions section.

``while`` Loop Syntax
---------------------

The general syntax of a ``while`` loop looks like this:

::

   while boolean expression:
      loop body

A ``while`` loop continues to repeat as long as the boolean expression
evaluates to ``True``. This *condition* usually includes a value or variable
that is updated within the loop. Eventually, the condition becomes ``False``,
and the loop stops.

Just like with ``for`` loops, the body of a ``while`` loop must be indented,
and it may contain any number of statements.

.. admonition:: Example

   The following loop repeats until ``total < 1000`` returns ``False``:

   .. sourcecode:: Python

      total = 0
      increase_by = 14

      while total < 1000:
         total += increase_by
         print(total)

Control Flow
------------

We can visualize the program flow of a ``while`` loop as follows.

.. figure:: figures/while-loop-flow.png
   :alt: Diagram showing the control flow through a while loop.

   Flow of execution of a ``while`` loop

#. Python evaluates the condition, which returns a value of ``True`` or
   ``False``.
#. If the condition is ``False``, exit the ``while`` loop and continue
   the program at the next statement after the loop body.
#. If the condition is ``True``, run the loop body and then go back to step 1.

``for`` Loops Rewritten as ``while`` Loops
------------------------------------------

We can use ``while`` to create any type of loop we want, including anything we
previously did with a ``for`` loop. For example, consider our first ``for``
loop that printed the numbers 0 - 20:

.. sourcecode:: python
   :linenos:

   for num in range(21):
      print(num)

This can be rewritten as a while loop:

.. sourcecode:: python
   :linenos:

   num = 0

   while num < 21:
      print(num)
      num += 1

Instead of using the ``range`` function to produce the values for ``num``, we
need to produce them ourselves in a ``while`` loop. To do this, *before*
starting the loop, we create the variable ``num`` and assign it a value of
``0``. Every iteration, line 5 increases ``num`` by 1. Eventually, ``num``
increases enough to make the condition ``num < 21`` false, and the loop ends.

``num`` plays the same role as the loop variable in the ``for`` loop, but we
need to manage its value ourselves. The ``for`` and ``while`` loops in the
examples above do *exactly* the same thing, but they solve the task slightly
differently.

If we imagine giving instructions to someone, the ``for`` and ``while``
approaches might sound something like:

#. **For**: Repeat this task for each number 0 - 20.
#. **While**: Repeat this task as long as the number is less than 21.

Try It!
^^^^^^^

Let's convert this ``for`` loop into the equivalent ``while``.

.. sourcecode:: python
   :linenos:

   letters = 'abcdefghijklmnopqrstuvwxyz'
   for_string = ''
   num_letters = 8

   for index in range(num_letters):
      for_string += letters[index]

   print(for_string)  # Displays 'abcdefgh'

Do the following in the editor below:

#. On line 5, define a counter variable called ``index``. Assign it a value of
   ``0``.
#. Next, code the ``while`` statement. Here are two possibilities:

   - ``while index < num_letters:``
   - ``while len(while_string) < num_letters:``

#. Inside the loop, update ``while_string``. Look at line 6 in the ``for`` loop
   for a hint about how to do this.
#. Also inside the loop, increase the value of ``index`` by 1.
#. Run the program to verify that it prints ``abcdefgh`` when
   ``num_letters = 8``.

.. raw:: html

   <iframe height="500px" width="100%" src="https://repl.it/@launchcode/LCHS-Rewrite-for-as-while?lite=true" scrolling="no" frameborder="yes" allowtransparency="true" allowfullscreen="true"></iframe>

Input Validation
----------------

``while`` loops require a little more effort to code than ``for`` loops, but
``while`` loops tend to be more flexible.

We can replace ANY ``for`` loop with a ``while``, but the reverse is NOT true.
Many ``while`` loops can be converted into ``for`` loops, but there are some
instances where only a ``while`` loop will work. Let's look at one example of
this.

.. index:: ! input validation

.. admonition:: Try It!

   This program is an example of **input validation**. It prompts the user to
   enter a positive number. If the user enters ``0`` or any negative number,
   then they see an error message and are prompted again within the body of the
   loop. If the user keeps entering invalid numbers, the loop continues to
   iterate. As soon as the user chooses a valid number, the loop ends.

   .. raw:: html

      <iframe height="450px" width="100%" src="https://repl.it/@launchcode/LCHS-While-Input-Validation?lite=true" scrolling="no" frameborder="no" allowtransparency="true"></iframe>

This example shows the additional flexibility provided by ``while`` loops.
``for`` loops iterate a specific number of times, but in this case we have no
way of knowing how many times we need to prompt the user for a number. By
setting a single condition (``num_choice <= 0``) we can keep the ``while`` loop
going until the condition returns ``False``.

Check Your Understanding
------------------------

.. admonition:: Question

   You can rewrite any ``for`` loop as a ``while`` loop.

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, true)"> True</li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> False</li>
      </ol>
      <p id="Q1"></p>

.. Answer = True

.. admonition:: Question

   You can rewrite any ``while`` loop as a ``for`` loop.

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> True</li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, true)"> False</li>
      </ol>
      <p id="Q2"></p>

.. Answer = False

.. admonition:: Question

   Which of the following will cause this ``while`` loop end? Select ALL that
   apply.

   .. sourcecode:: python
      :linenos:

      username = ''

      while len(username) <= 5:
         username = input("Enter a username: ")

   .. raw:: html
      
         <ol type="a">
            <li><span id = "Option a" onclick="highlight('Option a', false)">"Bob3"</span></li>
            <li><span id = "Option b" onclick="highlight('Option b', true)">"Anaconda"</span></li>
            <li><span id = "Option c" onclick="highlight('Option c', true)">"Willmore Crane Hastings III"</span></li>
            <li><span id = "Option d" onclick="highlight('Option d', false)">"Sally"</span></li>
            <li><span id = "Option e" onclick="highlight('Option e', true)">"LaunchCode"</span></li>
         </ol>

.. raw:: html

   <script type="text/JavaScript">
      function highlight(id, answer) {
         text = document.getElementById(id).innerHTML
         if (answer) {
            document.getElementById(id).style.background = 'lightgreen';
            document.getElementById(id).innerHTML = text + ' - Correct!';
         } else {
            document.getElementById(id).innerHTML = text + ' - Nope!';
            document.getElementById(id).style.color = 'red';
         }
      }

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
