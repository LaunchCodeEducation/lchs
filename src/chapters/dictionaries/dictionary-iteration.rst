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

.. _key-value-iteration:

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

Check Your Understanding
------------------------

.. admonition:: Question

   Given the code:

   .. sourcecode:: python
      :linenos:

      comics = {
         'Georgia Dunn' : 'Breaking Cat News',
         'Jan Eliot' : 'Stone Soup',
         'Wiley Miller' : 'Non Sequitur',         
         'Bill Watterson' : 'Calvin and Hobbs'
      }

      for key in comics.keys():
         print(key, comics[key])

   What is the value of ``comics[key]`` the *third* time through the loop?

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> <span style="color:#419f6a; font-weight: bold">'Wiley Miller'</span></li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> <span style="color:#419f6a; font-weight: bold">'Bill Watterson'</span></li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, true)"> <span style="color:#419f6a; font-weight: bold">'Non Sequitur'</span></li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> <span style="color:#419f6a; font-weight: bold">'Calvin and Hobbs'</span></li>
      </ol>
      <p id="Q1"></p>

.. Answer = c

.. raw:: html

   <script type="text/JavaScript">
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
