The ``main()`` Event
====================

The last skill new skill for this chapter is to learn why we need to add a
``main()`` function to our programs and modules. The best way to explain this
is to examine what happens when we do NOT include ``main()``.

The program below uses two files---``main.py`` and the module
``random_select.py``.

A Sample Program With One Module
--------------------------------

Let's pretend that we want to create a program that gives us information about
student scores. We started by coding the ``find_average_score`` and the
``create_report`` functions. Now we want to test these functions by sending
in lists of numbers.

In lines 20 - 21, we call ``find_average_score`` with a list of numbers with a
known average (3) and then print the result.

In line 23, we create a list of 8 random scores with values ranging from 90 -
100. In line 24, we call ``create_report`` and send it the ``pretend_scores``
list so we can check the format of the returned string.

.. admonition:: Example

   Let's see how well our program works. Run the code as-is and examine the
   output.

   .. raw:: html

      <iframe height="900px" width="100%" src="https://repl.it/@launchcode/Why-Use-Main?lite=true" scrolling="no" frameborder="yes" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

   Wait... what? The output contains three lists that we don't expect from our
   code we wrote in lines 20 - 24.

   #. Comment out lines 20 - 24, then re-run the program.
   #. Wait... what? The two ``print`` statements are commented out, but output
      still appears in the console!

Loose Statements
----------------

OK, we have a problem with our program, but it's not with ``main.py``. Click on
the *Files* icon in the top-left corner of the editor. This will show a list of
the two files that make up this program.

Click on ``random_lists.py`` tab to show its code in the editor.

.. index::
   single: statement; loose

The module contains five functions, but the issue is at the bottom of the file.
Scroll to the end of the code to find the 8 statements in lines 44 - 51. We
call these **loose statements** because they are not part of any function.

Sometimes loose statements are just leftover commands that we used to test our
defined functions. However, most of the time the loose code is needed to run
the program. It could prompt the user for information, call the functions in
the proper order, set up a required drawing space, etc.

In this case, the loose code contains three ``print`` statements, and these
create the unexpected output. This brings up a very important point:

   Loose statements ALWAYS run, even if none of the functions in the program
   get called.

In ``main.py``, by running ``import random_lists`` on line 1, the loose code in
the module executes. This is why we see three lists appear in the console even
if we remove all ``print`` commands in ``main.py``.

We need to learn how to deal with loose statements so that they only run when
we want them to.

Add a ``main()`` Function
-------------------------

In our example, the loose code in ``random_lists`` is just there for testing.
We could simply remove it, but let's deal with it in a better way.

Loose code winds up in a program because it does not fit into any of the
defined functions. However, these statements DO relate to each other because
they serve the same purpose---they control the main job of the program.

Update the code in ``random_lists`` by defining a ``main()`` function before
the loose code. Next, indent the loose lines so that they move into the
function:

.. sourcecode:: Python
   :lineno-start: 44

   def main():
      numbers = create_random_number_list(8, -10, 10)
      no_repeat_numbers = create_unique_number_list(5, 0, 10)
      letters = create_random_letter_list(8)
      numbers.sort()
      no_repeat_numbers.sort()
      print(numbers)
      print(no_repeat_numbers)
      print(letters)

``main()`` requires no parameters, nor does it need a return statement.

Return to ``main.py`` and uncomment lines 20 - 24. Click *Run* and notice that
the extra output disappears! Since the loose code from ``random_lists`` is now
inside its own function, it will only run if we call ``main()``.

.. admonition:: Try It!

   In ``main.py``, add the statement ``random_lists.main()`` and re-run the
   program. The three extra lists should appear.

Add ``main()`` to ``main.py``
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Lorem ipsum...

Alternate Wording
-----------------

Using functions is a GREAT idea. So is using modules. However, in both cases
there may be some "loose" code that winds up at the bottom of our work. These
statements may be necessary to run the complete program, or they might be
leftover from testing the code. Either way, we need to learn how to deal with
statements that don't seem to fit inside any of our defined functions.

Let's take a look at an example of this:

.. admonition:: Example

   .. sourcecode:: Python
      :linenos:

      import random

      def create_random_number_list(num_elements, start_value, end_value):
         new_list = []
         for element in range(num_elements):
            new_list.append(random.randint(start_value, end_value))        
         
         return new_list

      numbers = create_random_number_list(8, -10, 10)
      numbers.sort()
      print(numbers)

Notice that we first ``import`` the required module. Next, we define the
``create_random_number_list`` function. Finally, we include three statements
to call the function, sort the list, and print the final collection.

Most of the work happens inside the function, but we still need the last three
lines of code to get things done. They perform the main job of the program
(printing a sorted list of numbers).

Avoid Loose Statements
----------------------

In many programming languages, like Java and C#, we are not allowed to leave
statements sitting alone at the bottom of the program. Python is more
forgiving, but as a best practice we should keep ALL statements inside of a
defined function.

In our example, where should we put the last three lines of code? They relate
to each other because they perform the *main* job of the program. This gives us
a good name for these commands:

.. admonition:: Try It!

   Run the following program.

   .. todo:: Insert interactive repl here (main function)!

   .. sourcecode:: Python
      :linenos:

      import random

      def create_random_number_list(num_elements, start_value, end_value):
         new_list = []
         for element in range(num_elements):
            new_list.append(random.randint(start_value, end_value))        
         
         return new_list

      def main():
         numbers = create_random_number_list(8, -10, 10)
         numbers.sort()
         print(numbers)

   Notice that nothing appears in the console! Remember that defining a
   function does NOT run it.

   #. Call the function by adding ``main()`` on line 15, then run the program
      again. Output should appear this time.
   #. Note that on line 10, we define ``main`` with no parameters.
   #. Note that on line 15, we do not include any arguments in the function
      call.

Why Avoid Loose Statements?
---------------------------

Might be thinking that adding ``main()`` provides little benefit...

Show example of unwanted output (print statements) and/or sorting when
using an imported function...

How to call ``main()`` only when it's part of ``main.py``... 

Avoids accidental shadowing...
