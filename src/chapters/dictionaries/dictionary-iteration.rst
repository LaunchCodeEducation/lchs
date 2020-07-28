.. _dictionary-iteration:

Iterating Through Dictionaries
==============================

Many times in this book, we looped through the characters in a string or the
elements in a list without using the index values.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      my_string = 'Rutabagas!'
      numbers = [33, -25, 3.14, 86, 1168, 42, 6.022e23]

      for character in my_string:
         print(character)
      
      total = 0
      for number in numbers:
         total += number*2

Each time the loop body repeats, the loop variable---``character`` or
``number``---gets assigned the next value in the collection.

We can do something similar with dictionaries.

Loop by Keys or Values
----------------------

To loop through a dictionary, we need to specify whether to assign the loop
variable the keys or the values from the collection. To do this, we use the
``keys()`` or ``values()`` method in the ``for`` statement:

.. sourcecode:: python
   :linenos:

   for key in dictionary_name.keys():
      # Loop body...

   for value in dictionary_name.values():
      # Loop body...

In the first ``for`` loop, each time the code repeats, the loop variable
``key`` gets assigned one of the key names from the dictionary. In the second
loop, the variable ``value`` gets assigned a new value each iteration.

.. admonition:: Note

   We do not have to use the name ``key`` or ``value`` for the loop variable,
   but doing so helps keep our code clear.
   
   When we read our code, the name reminds us which half of the key/value pair
   gets assigned to the loop variable.

.. admonition:: Try It!

   Run the following program to see how iterating through a dictionary works.

   .. raw:: html

      <iframe src="https://trinket.io/embed/python3/2062905b4b" width="100%" height="550" frameborder="1" marginwidth="0" marginheight="0" allowfullscreen></iframe>
   
   Try adding or removing key/value pairs to change the output.

Note that in lines 21 and 26, we access each value in the dictionary by using
bracket notation and the loop variable ``key``. Each iteration, ``key``
represents a new label from ``comics``, so ``comics[key]`` accesses a different
value each time the loop repeats.

.. admonition:: Try It!

   What happens if we forget to attach the ``keys()`` or ``values()`` method in
   the ``for`` statement?  Let's find out!

   Run the following program to see how Python deals with a missing method.

   .. raw:: html

      <iframe src="https://trinket.io/embed/python3/1f17f7d307" width="100%" height="300" frameborder="1" marginwidth="0" marginheight="0" allowfullscreen></iframe>

Aha! By default, Python iterates through a dictionary by using the key names.

Loop by Key/Value Pairs
^^^^^^^^^^^^^^^^^^^^^^^

The ``items()`` method returns each key/value pair as a unit, and it allows us
to assign BOTH the key and value from the dictionary to separate variables. The
general syntax for this is:

.. sourcecode:: python

   for (key, value) in dictionary_name.items():

In the ``for`` statement, we define a pair of variables ``(key, value)`` to
hold a key name and its linked value from the dictionary. Each iteration, these
two variables represent a new key/value pair from the collection.

.. admonition:: Example

   Compare the following two loops, which do exactly the same thing:

   .. sourcecode:: python
      :linenos:

      comics = {
         'Gary Larson' : 'The Far Side',
         'Terri Libenson' : 'Pajama Diaries',
         'Hilary B. Price' : 'Rhymes with Orange',
         'Jim Toomey' : "Sherman's Lagoon"
      }

      # Iterate by keys, and print out the dictionary key/value pairs:
      for key in comics.keys():
         print(key, comics[key])

      # Iterate by key/value pairs:
      for (key, value) in comics.items():
         print(key, value)

   By defining a pair of variables, we can access the values from the
   dictionary without needing to use bracket notation. On line 14, the variable
   ``value`` replaces ``comics[key]`` in our code. 

Accumulator Pattern
-------------------

We can add key/value pairs one at a time to an empty dictionary using bracket
notation:

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      eng_to_pirate = {}

      eng_to_pirate['Hello'] = 'Ahoy'
      eng_to_pirate['your'] = 'yer'
      eng_to_pirate['there'] = 'yonder'
      eng_to_pirate['element 18'] = 'Ar'

      print(eng_to_pirate)

   **Console Output**

   ::

      {'Hello': 'Ahoy', 'your': 'yer', 'there': 'yonder', 'element 18': 'Ar'}

A more efficient way would be to use the accumulator pattern to add new
key/value pairs. Let's play with a couple of examples to practice this.

.. admonition:: Try It!

   The following program builds the ``vowel_count`` dictionary by adding a new
   key/value pair each time the loop repeats. Each character from the string
   ``'aeiou'`` becomes a key in the dictionary, which gets linked to an integer
   value.

   #. Line 5 creates an empty dictionary and assigns it to the variable
      ``vowel_counts``.
   #. Line 7 creates a new key/value pair in ``vowel_counts``. Each key is one
      character from ``vowels``, and its value is how often that letter occurs
      in the ``guide`` string.

   .. raw:: html

      <iframe src="https://trinket.io/embed/python3/67ba69e3aa" width="100%" height="300" frameborder="1" marginwidth="0" marginheight="0" allowfullscreen></iframe>

   **Now try:**

   #. Indent line 9 to put the ``print`` statement inside the loop. Run the
      program to see how ``vowel_counts`` grows each time the loop repeats.
   #. Replace ``guide`` with ``games``.
   #. Use a different string in the ``for`` statement to count different
      letters or other characters. (As a good Python coder, you should change
      your variable names once you stop counting vowels).

The previous example took the characters from the string ``'aeiou'`` and turned
them into dictionary keys. We used items from one collection (a string) to help
us build a new dictionary.

The next example combines the elements of two lists into a single dictionary.

.. admonition:: Try It!

   Let's build an English-to-pirate translation dictionary! We will use English
   words as keys and pirate words for the values.

   Feel free to add your own words to each list! However, be sure to keep both
   lists the same length.

   .. raw:: html

      <iframe src="https://trinket.io/embed/python3/8ec43b09a7" width="100%" height="350" frameborder="1" marginwidth="0" marginheight="0" allowfullscreen></iframe>

   #. Since we pull elements from two different lists, we need to assign
      *index* values (0, 1, 2...) to the loop variable. This allows us to match
      the correct words from each list.
   #. On line 9, ``english_words[index]`` accesses one element from the
      ``english_words`` list, and it uses that element to define a new key. For
      example, the first time through the loop, the left hand side of line 9
      evaluates as:
      
      a. ``eng_to_pirate[english_words[index]]``
      b. ``eng_to_pirate[english_words[0]]``
      c. ``eng_to_pirate['hello']``

   #. The right hand side of line 9 uses the same index value, but it pulls an
      element from the ``pirate_words`` list:

      a. ``pirate_words[index]``
      b. ``pirate_words[0]``
      c. ``'ahoy'``

   #. For index value 0, line 9 reduces to ``eng_to_pirate['hello'] = 'ahoy'``,
      and this adds the ``'hello' : 'ahoy'`` pair to the ``eng_to_pirate``
      dictionary.

We can also use the accumulator pattern to perform an operation on each value
in a dictionary.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      exam_scores = {'exam_1' : 95, 'exam_2' : 90.7, 'exam_3' : 88.3}

      total = 0
      for key in exam_scores:
         total += exam_scores[key]
      
      average = total / len(exam_scores)
      rounded_average = round(average, 1)
      print("The average result is {0}%.".format(rounded_average))

   **Console Output**

   ::

      The average result is 91.3%.

Check Your Understanding
------------------------

Lorem ipsum...
