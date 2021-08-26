Chapter 12: Python Dictionaries 
===============================

The answers on this page show ONE way to solve the :ref:`exercises <dictionaries-exercises>`.
However, there are usually OTHER ways to accomplish the same thing. This is OK!

   A suggested solution is ONE way to solve the problem, not the ONLY way.


Chapter Sandbox
---------------

Use the editor below to test out any of the solutions!

.. raw:: html

	<iframe src="https://trinket.io/embed/python3/5e09fffbac" width="100%" height="400" frameborder="1" marginwidth="0" marginheight="0" allowfullscreen></iframe>

Solutions
---------
Part A: Search a Dictionary
^^^^^^^^^^^^^^^^^^^^^^^^^^^

The ``flavors`` dictionary contains entries that pair different ice cream
flavors with their cost per scoop. Your job is to do the following:

1. Write a function called ``return_cost`` that takes a dictionary and flavor
   choice as parameters.
   
   a. The function searches the dictionary for the flavor and returns its cost.
   b. If the flavor is not in the dictionary, return a value of ``0``.

2. After coding the ``return_cost`` function, run the program and examine the
   output. Make sure your function behaves as expected before moving to the
   next step. Don't forget to assign different strings to the ``choice``
   variable! 
3. Write a function called ``fanciest_flavor`` that takes a dictionary as a
   parameter. The function should return the key name for the most expensive
   choice in the dictionary.
4. Uncomment the 3 indicated lines in ``main()``, then run the program several
   times and examine the output. Change the prices in ``flavors`` after each
   run to make sure your function correctly identifies the most expensive ice
   cream flavor.

Part B: Keys from a Collection
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Use the accumulator pattern to add new key/value pairs to an empty dictionary.

1. Write a function called ``assign_tickets`` that takes a list of names as a
   parameter.
2. The function should take each name from the list and use it to create a key
   in the dictionary.
3. For the value of each key, assign a random integer from 100-500.

4. Return the new dictionary.
5. In ``main()``, call the ``assign_tickets`` function and assign the result to
   a ``ticket_holders`` variable.

Print ``ticket_holders`` to check that your code works as expected. Your output
should look something like:

::

   {'Caleb': 192, 'Naomi': 490, 'Owen': 465, 'Ava': 248, 'Aaron': 421, 'Lydia': 306}

Part C: Modify Values
^^^^^^^^^^^^^^^^^^^^^

Oh no! Ticket numbers 100-199 were supposed to be held back for VIPs. You need
to reassign tickets to anyone who was given one of the reserved seats. Use the
editor in part B as you update your code.

Call the function ``fix_tickets``, and use ``ticket_holders`` as the argument.
The ``fix_tickets`` function should:

1. Accept a dictionary as a parameter.
2. Loop through the dictionary and check each ticket number to see if it is in
   the range 100-199 (including the end points).
3. For a ticket within the range, increase its value by ``500`` and reassign it
   to the key.
4. Unless you cloned the dictionary, there is no need to return the updated
   collection.

To check your code, be sure to print ``ticket_holders`` before and after
calling the ``fix_tickets`` function.

**Sample Output:**

::

   Before: {'Caleb': 168, 'Naomi': 205, 'Owen': 193, 'Ava': 161, 'Aaron': 246, 'Lydia': 330}
   After: {'Caleb': 668, 'Naomi': 205, 'Owen': 693, 'Ava': 661, 'Aaron': 246, 'Lydia': 330}

Part D: Counting Characters
^^^^^^^^^^^^^^^^^^^^^^^^^^^

Write a function called ``character_count`` that counts how many times each
character appears in a string.

The function should:

1. Accept a string as a parameter.
2. Create an empty dictionary called ``counts``.
3. Loop through the string and check each character.

   a. If the character does NOT exist in as a key in ``counts``, add it and
      assign it a value of ``1``.
   b. If the character DOES exist as a key in ``counts``, increase its value by
      one.

4. Return the completed ``counts`` dictionary and assign it to a ``results``
   variable in ``main()``.

The counting should be *case-insensitive*. For example, ``'a'`` and ``'A'``
both count as the same letter.

Be sure to print the returned dictionary to check your code.

::

   #. ``"Python ROCKS!"`` returns ``{'p': 1, 'y': 1, 't': 1, 'h': 1, 'o': 2, 'n': 1, ' ': 1, 'r': 1, 'c': 1, 'k': 1, 's': 1, '!': 1}``.
   #. ``"Balloons, bookkeepers, and bubbles."`` returns ``{'b': 5, 'a': 2, 'l': 3, 'o': 4, 'n': 2, 's': 3, ',': 2, ' ': 3, 'k': 2, 'e': 4, 'p': 1, 'r': 1, 'd': 1, 'u': 1, '.': 1}``.

Part E: Use a List to Sort Key/Value Output
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Now display the character count result in a cleaner way. Update your code in
the part D editor.

1. In the ``main()`` function, loop through the ``results`` dictionary and
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
2. Modify your code to print a key/value pair ONLY IF the character is a
   letter.
3. Modify your code again, but this time display the character counts in
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
