Chapter 7: Stringing Characters Together
========================================

The answers on this page show ONE way to solve the :ref:`exercises <strings-exercises>`.
However, there are usually OTHER ways to accomplish the same thing. This is OK!

    A suggested solution is ONE way to solve the problem, not the ONLY way.

Chapter Sandbox
---------------

Use the editor below to test out any of the solutions!

.. raw:: html

    <iframe src="https://trinket.io/embed/python3/fa4912a3e8" width="100%" height="400" frameborder="1" marginwidth="0" marginheight="0" allowfullscreen></iframe>

Solutions
---------
.. _chp7part1: 
Part One: Bracket Notation
^^^^^^^^^^^^^^^^^^^^^^^^^^

1. Identify the result for each of the following statements:

   a. ``'Characters'[8]`` = r
   b. ``"Strings are sequences of characters."[5]`` = g
   c. ``len("Wonderful")`` = 9
   d. ``len("Do spaces count?")`` = 16

2. Use bracket notation to:

   a. Print a slice of the first 12 characters from
      ``"Strings_are_sequences_of_characters."``

        .. sourcecode:: Python
            :linenos:

            text = 'Strings_are_sequences_of_characters.'
            print(text[:12])

   c. Print a slice of the middle 12 characters from the same string.

        .. sourcecode:: Python
            :linenos:

            #simple solution that solves for just text = 'Strings_are_sequences_of_characters.'
            print(text[12:24])


3. Use index values to loop *backwards* through a string:

   a. First, print one letter per line.

        .. sourcecode:: Python
            :linenos:

            max_index = len(word) - 1
            for index in range(max_index, -1, -1):
            print(word[index])
         
   b. Next, instead of one letter per line, use the accumulator pattern to build
      up and print the reversed string. 

        .. sourcecode:: Python
            :linenos:

            word = "tomato"
            new_word = ""
            for index in range(max_index, -1, -1):
                new_word += word[index]
    
            print (new_word)

   c. Finally, use concatenation to print the combination of the original and
      reversed string. 

        .. sourcecode:: Python
            :linenos:

            print(word + new_word)

:ref:`Back to the exercises <strings-exercises>`.

.. _chp7part2:      
Part Two: String Methods and Operations
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. The ``len()`` function returns the number of characters in a string.

   a. Use ``str()`` to change ``num`` from an ``int`` to a string data type.
   b. Print the length (number of digits) in ``num``.
   c. Modify your code to print the number of digits in a ``float`` value (e.g.
      ``num = 123.45`` has 5 digits but a length of 6). The digit count should
      NOT include the decimal point.
   d. What if ``num`` could be EITHER an integer or a decimal? Add an ``if/else``
      statement so your code can handle both cases.  (Hint: Consider using the
      ``find()`` method or the ``in`` operator to check if ``num`` contains a
      decimal point).


2. Given ``word = 'bag'``:

   a. Set up a loop to iterate through the string of lowercase vowels,
      ``'aeiou'``.
   b. Inside the loop, create a new string from ``word``, but with a different
      vowel. Use the ``replace()`` string method.
   c. Print the new string.
   d. Properly done, your output should look something like this:

      ::

         bag
         beg
         big
         bog
         bug
   
   e. Try other words besides ``'bag'``!

      `Code it at repl.it <https://repl.it/@launchcode/LCHS-Strings-Exercises-Part-2-2>`__, or
      `Code it at Trinket <https://trinket.io/python/3d9aa1cac1?showInstructions=true>`__.

3. Consider a string that represents a strand of DNA:
   ``dna = " TCG-TAC-gaC-TAC-CGT-CAG-ACT-TAa-CcA-GTC-cAt-AGA-GCT    "``. There
   are some typos in the string that you need to fix:

   a. Use the ``strip()`` method to remove the leading and trailing whitespace,
      and then print the result.
   b. Change all of the letters in the DNA string to UPPERCASE and print the
      result.
   c. Note that you need to *reassign* the changes back to the ``dna`` variable in order to see them printed. 
      Apply these fixes to your code so that ``print(dna)`` prints the DNA strand in UPPERCASE
      with no whitespace.

4. Let's use string methods to do more work on the same DNA strand:

   a. Use ``replace()`` to remove the sequence ``'GCT'``, and then print the altered
      strand. Don't forget about the extra hyphen!
   b. Look for the sequence ``'CAT'`` with ``find()``. If found print, ``'CAT
      found'``, otherwise print, ``'CAT NOT found'``.
   c. Use ``count()`` to find the number of hyphens (``-``) in the string, then
      print the number of *genes* (in this case, a gene is a set of 3 letters) in the DNA strand. Note
      that the number of genes will be 1 more than the number of hyphens. 

:ref:`Back to the exercises <strings-exercises>`.

.. _chp7part3:  

Part Three: String Formatting
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. Assign your favorite, school-appropriate number and word to two variables.
   
   a. Use ``format()`` and index values to print the string,
      ``"Here is my number: ___, and here is my word: ___, and here is my
      number again: ___."``
   b. Print the string, ``"Here is my word 3 times: ___/___/___, and here is my
      number squared: ___."``

      
2. For part 2, exercise 4, use an f-string to print the output
   ``"The DNA string is ___ characters long and contains ___ genes."`` Fill in
   the blanks with the length of the string and the number of genes.

3. The following code sample works, but it can be improved.

   a. Assuming that ``advice`` remains a string, when will the code produce the
      wrong output?
   b. Why will the code do this?
   c. What should the programmer do to fix the code?

:ref:`Back to the exercises <strings-exercises>`.

