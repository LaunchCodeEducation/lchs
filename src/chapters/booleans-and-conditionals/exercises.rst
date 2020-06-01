Exercises: Booleans and Conditionals
====================================

If your teacher has added to you a *repl.it classroom*, complete the exercises
there. Otherwise, follow the links to *standard repl.it* (no auto-grader).

Part A: Basic Selection
-----------------------

If you are NOT assigned to a repl.it classroom, follow this link for the
`part A <https://repl.it/@launchcode/Conditional-Exercises-Part-A>`__ starter
code.

``if`` Only
^^^^^^^^^^^

Prompt the user to enter a word and store the result in ``user_entry``:

.. sourcecode:: python

   user_entry = input('Enter a word: ')

#. Use a conditional to check the length of the word. If longer than 5
   characters, print, ``"___ is longer than 5 characters."`` Otherwise, print
   nothing. (Note: Fill in the blank with the value of ``user_entry``).

Binary Selection
^^^^^^^^^^^^^^^^

Prompt the user to enter a number:

.. sourcecode:: python

   num_entry = input('Enter a number larger than 100: ')

2. Check if ``num_entry`` is 100 or larger. If so, print, ``"Valid entry!"``
   Else print, ``"Number too small."``
#. Check if ``user_entry`` is all lowercase. If so, print, ``"___ is all
   lowercase."`` Else, print, ``"___ is NOT all lowercase."`` Fill in the blank
   with the value of ``user_entry``. (*Hint*: Take advantage of the
   ``.lower()`` string method).

The ``in`` keyword can be used as another comparison operator.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      print('ana' in 'banana')
      print('z' in 'apple')

   **Console Output**

   ::

      True
      False

   The string ``ana`` is present within ``banana``, while there is no
   ``z`` character within ``apple``.

4. Use the ``in`` operator to check if ``user_entry`` starts with a vowel. If
   so, print, ``"___ starts with a vowel."`` Else, print, ``"___ does NOT start
   with a vowel."``

Part B: Logical Operators
-------------------------

Use the logical ``and``, ``or``, and ``not`` operators in the following
exercises (`part B <https://repl.it/@launchcode/Conditional-Exercises-Part-B>`__
starter code).

#. Given an integer, check to see if the number is even and divisible by 5.
   Print an appropriate message depending on the result.

#. Given a string, print, ``"Exterior vowel found!"`` if the string begins or
   ends with a vowel. Otherwise, print, ``"Consonants all around!"``

#. Refactor the following code to check if ``text`` does NOT start with a
   capital letter or vowel. How does making this change affect the ``if/else``
   code blocks?

   .. sourcecode:: python
      :linenos:

      text = 'conditioNals Affect control FLOW'

      if text[0].upper() == text[0] or text[0].lower() in vowels:
         print("'{0}' starts with a vowel OR capital letter".format(text))
      else:
         print("Fix '{0}' to start with a capital letter or vowel".format(text))

#. If ``num = 5``, indicate whether each of following expressions returns
   ``True`` or ``False``.

   .. sourcecode:: python
      :linenos:

      num >= 0 and num*2 <= 50 and num%2 == 0
      num >= 0 or num*2 <= 50 or num%2 == 0
      num >= 0 and num*2 <= 50 or num%2 == 0
      num >= 0 or num*2 <= 50 and num%2 == 0
      not num < 0 and num%3 != 0
      not (num%3 == 0 or num*4 >= 20)

Part C: Chained Conditionals
----------------------------

Use this starter code for `parts C and D <https://repl.it/@launchcode/Conditional-Exercises-Parts-C-and-D>`__.

#. For ``if/elif/else`` statements, the *order* of the checks is important.
   The following code should determine if a number is divisible by 2, 3, both
   or neither, but as written it does not behave as we want. Rearrange the
   order of the ``if``, ``elif``, and ``else`` code blocks as needed to give
   the desired results.

   .. sourcecode:: python
      :linenos:

      num = 6 # Try the values 10, 15, and 7 as well.

      if num%2 == 0:
         print(num, "is divisible by 2.")
      elif num%3 == 0:
         print(num, "is divisible by 3.")
      elif num%2 == 0 and num%3 == 0:
         print(num, "is divisible by 2 and 3.")
      else:
         print(num, "is NOT divisible by 2 or 3.")

   For ``num = 6``, the output should be ``'6 is divisible by 2 and 3.'``

#. Given the score on an exam, use a chained conditional to assign it the
   proper letter grade. Assume a standard 10-point scale (A = 100 - 90, B =
   89 - 80, C = 79 - 70, etc.). Print the results as ``___% = ___``. Fill in
   the first blank with the score and the second blank with the letter grade.
#. Write code to help you pick an activity based on the current weather.
   Consider two variables, one for temperature (``hot`` or ``cold``) and one
   for how wet it is (``rainy`` or ``dry``). If the weather is hot and rainy,
   your code should tell you to watch Netflix. For hot and dry conditions, it
   should tell you to go swimming. If cold and rainy, it should tell you to
   get under a blanket and read. If it is cold and dry, it should tell you to
   hang out with a friend.

Part D: Nested Conditionals
---------------------------

4. Ask the user for their lunch selection - ``burger`` or ``salad``. If they
   choose ``salad``, ask them for a dressing option (``ranch`` or ``italian``).
   If they choose ``burger`` ask them if they want cheese (``yes`` or ``no``).
   Print out their final order.
#. Each option has a different price. Add a ``cost`` variable to your code and
   calculate the bill for the lunch order. Include this in the print
   statement.
#. Assume you want to add a drink question for the customer. Where would be the
   BEST place to ask this question? EXPLAIN your reasoning for your choice.

   a. Inside the nested statements before the cheese/dressing questions.
   b. Inside the nested statements after the cheese/dressing question.
   c. As a separate conditional outside of the nested statements.
