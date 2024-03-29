.. _dictionaries-exercises:

Exercises: Dictionaries
=======================

If your teacher added you to a :ref:`Trinket course <trinket-course-assignments>`, login to your account
to access the starter code for each exercise.

Otherwise, use the links below to code in your own free account.

.. admonition:: Note

   The code editors embedded in the exercises all include a *Remix* button in
   the upper right corner which will save the code to your Trinket account. For
   the matching repl.it code, click these links:

   #. `Part A <https://repl.it/@launchcode/LCHS-Dictionary-Exercises-Part-A>`__
   #. `Parts B and C <https://repl.it/@launchcode/LCHS-Dictionary-Exercises-Parts-B-and-C>`__
   #. `Parts D and E <https://repl.it/@launchcode/LCHS-Dictionary-Exercises-Parts-D-and-E>`__

Part A: Search a Dictionary
---------------------------

The ``flavors`` dictionary contains entries that pair different ice cream
flavors with their cost per scoop. Your job is to do the following:

#. Write a function called ``return_cost`` that takes a dictionary and flavor
   choice as parameters.
   
   a. The function searches the dictionary for the flavor and returns its cost.
   b. If the flavor is not in the dictionary, return a value of ``0``.

#. After coding the ``return_cost`` function, run the program and examine the
   output. Make sure your function behaves as expected before moving to the
   next step. Don't forget to assign different strings to the ``choice``
   variable! 
#. Write a function called ``fanciest_flavor`` that takes a dictionary as a
   parameter. The function should return the key name for the most expensive
   choice in the dictionary.
#. Uncomment the 3 indicated lines in ``main()``, then run the program several
   times and examine the output. Change the prices in ``flavors`` after each
   run to make sure your function correctly identifies the most expensive ice
   cream flavor.

.. raw:: html

   <iframe src="https://trinket.io/embed/python3/e377c26043" width="100%" height="600" frameborder="1" marginwidth="0" marginheight="0" allowfullscreen></iframe>

:ref:`Check your solutions <chp12partA>`.

.. _Chp12Keys:

Part B: Keys from a Collection
------------------------------

Use the accumulator pattern to add new key/value pairs to an empty dictionary.

#. Write a function called ``assign_tickets`` that takes a list of names as a
   parameter.
#. The function should take each name from the list and use it to create a key
   in the dictionary.
#. For the value of each key, assign a random integer from 100-500.

   .. admonition:: Tip

      We are not worried about giving two people the same ticket number in this
      exercise. However, for a real event we would want to prevent this.

      Check out the :ref:`Unique Dictionary Values <unique-dict-values>`
      section in the ``Random Module`` appendix if you would like to avoid
      repeats in the values.

#. Return the new dictionary.
#. In ``main()``, call the ``assign_tickets`` function and assign the result to
   a ``ticket_holders`` variable.

Print ``ticket_holders`` to check that your code works as expected. Your output
should look something like:

::

   {'Caleb': 192, 'Naomi': 490, 'Owen': 465, 'Ava': 248, 'Aaron': 421, 'Lydia': 306}

.. raw:: html

   <iframe src="https://trinket.io/embed/python/494766d553" width="100%" height="500" frameborder="1" marginwidth="0" marginheight="0" allowfullscreen></iframe>

:ref:`Check your solutions <chp12partB>`.

.. _Chp12MV:

Part C: Modify Values
---------------------

Oh no! Ticket numbers 100-199 were supposed to be held back for VIPs. You need
to reassign tickets to anyone who was given one of the reserved seats. Use the
editor in part B as you update your code.

Call the function ``fix_tickets``, and use ``ticket_holders`` as the argument.
The ``fix_tickets`` function should:

#. Accept a dictionary as a parameter.
#. Loop through the dictionary and check each ticket number to see if it is in
   the range 100-199 (including the end points).
#. For a ticket within the range, increase its value by ``500`` and reassign it
   to the key.
#. Unless you cloned the dictionary, there is no need to return the updated
   collection.

To check your code, be sure to print ``ticket_holders`` before and after
calling the ``fix_tickets`` function.

**Sample Output:**

::

   Before: {'Caleb': 168, 'Naomi': 205, 'Owen': 193, 'Ava': 161, 'Aaron': 246, 'Lydia': 330}
   After: {'Caleb': 668, 'Naomi': 205, 'Owen': 693, 'Ava': 661, 'Aaron': 246, 'Lydia': 330}

:ref:`Check your solutions <chp12partC>`.

.. _Chp12CC:

Part D: Counting Characters
---------------------------

Write a function called ``character_count`` that counts how many times each
character appears in a string.

The function should:

#. Accept a string as a parameter.
#. Create an empty dictionary called ``counts``.
#. Loop through the string and check each character.

   a. If the character does NOT exist in as a key in ``counts``, add it and
      assign it a value of ``1``.
   b. If the character DOES exist as a key in ``counts``, increase its value by
      one.

#. Return the completed ``counts`` dictionary and assign it to a ``results``
   variable in ``main()``.

The counting should be *case-insensitive*. For example, ``'a'`` and ``'A'``
both count as the same letter.

Be sure to print the returned dictionary to check your code.

.. admonition:: Tip

   Here are some test strings and their results:

   #. ``"Python ROCKS!"`` returns ``{'p': 1, 'y': 1, 't': 1, 'h': 1, 'o': 2, 'n': 1, ' ': 1, 'r': 1, 'c': 1, 'k': 1, 's': 1, '!': 1}``.
   #. ``"Balloons, bookkeepers, and bubbles."`` returns ``{'b': 5, 'a': 2, 'l': 3, 'o': 4, 'n': 2, 's': 3, ',': 2, ' ': 3, 'k': 2, 'e': 4, 'p': 1, 'r': 1, 'd': 1, 'u': 1, '.': 1}``.

.. raw:: html

   <iframe src="https://trinket.io/embed/python/86e403e1a1" width="100%" height="550" frameborder="1" marginwidth="0" marginheight="0" allowfullscreen></iframe>

:ref:`Check your solutions <chp12partD>`.

.. _Chp12UseList:

Part E: Use a List to Sort Key/Value Output
-------------------------------------------

Now display the character count result in a cleaner way. Update your code in
the part D editor.

#. In the ``main()`` function, loop through the ``results`` dictionary and
   print each key/value pair on its own line. For ``"B-A-L-L-O-O-N-S!"``, the
   output would be:

   ::

      The character counts for 'B-A-L-L-O-O-N-S!' are:
      b: 1
      -: 7
      a: 1
      l: 2
      o: 2
      n: 1
      s: 1
      !: 1

   Be sure your output includes the introductory sentence.
#. Modify your code to print a key/value pair ONLY IF the character is a
   letter.
#. Modify your code again, but this time display the character counts in
   alphabetical order.
   
   a. Use the ``list`` function to create a list of the keys from the
      ``results`` dictionary.
   b. Sort the list, then use a loop to print the key/value pairs, one pair
      per line.

The final output for ``"B-A-L-L-O-O-N-S!"`` should be:

::

   The character counts for 'B-A-L-L-O-O-N-S!' are:
   a: 1
   b: 1
   l: 2
   n: 1
   o: 2
   s: 1

:ref:`Check your solutions <chp12partE>`.

