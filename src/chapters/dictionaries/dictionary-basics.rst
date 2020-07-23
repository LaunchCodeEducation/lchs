Dictionary Basics
=================

We learned that both lists and strings are examples of *ordered collections*.
They are built from smaller, individual pieces of data, each of which has its
own index value.

.. index:: ! dictionary

A third type of Python collection is called a **dictionary**. Dictionaries are
*unordered*, and they store data using sets of **key/value pairs**. Think of
a *key* just like a label or variable name. It *points to* a specific piece of
data, called the *value*.

The values in a dictionary may be of any data type, including lists and other
dictionaries. The keys, however, should either be ``int`` or ``str``. In most
cases, using strings is a better choice.

.. todo:: Add image comparing an indexed string/list vs. a dictionary.

Create a New Dictionary
-----------------------

There are several ways to create a new dictionary. The simplest is to wrap the
key/value pairs in curly braces ``{}``, with each pair separated from the
others by commas.

.. admonition:: Example

   .. sourcecode:: Python
      :linenos:

      my_dictionary = {'name' : 'Bob', 'id_number' : 1234, 'scores' : [95, 73, 88]}
      empty_dictionary = {}

Note the following:

#. Inside the curly braces, colons ``:`` separate the key/value pairs, with the
   keys on the left and the values on the right.
#. Just like lists, we can define an empty dictionary using a pair of braces.

To help make our code more readable, a useful trick is to define a dictionary
with only one key/value pair on each line.

.. admonition:: Example

   .. sourcecode:: Python
      :linenos:

      my_dictionary = {
         'name' : 'Bob',
         'id_number' : 1234,
         'scores' : [95, 73, 88]
      }

Accessing Values
----------------

Just like strings and lists, we access dictionary values by using square
brackets ``[]``. Unlike strings and lists, dictionaries do NOT use index
values. To access the string ``'Bob'`` in ``my_dictionary``, we place the name
of the key inside the brackets, ``my_dictionary['name']``.

.. admonition:: Try It!

   Experiment with the dictionary syntax to add or print values from
   ``my_dictionary``.

   #. Add at least three new key/value pairs to ``my_dictionary``.
   #. Note that line X prints the entire dictionary (with braces) to the
      console.
   #. Change the key in line Y to print different values from
      ``my_dictionary``.
   #. In line Y, try using a key name that does NOT exist in the dictionary.

   .. todo:: Add interactive repl here (dictionary syntax).

What are "Keys"?
----------------

Lorem ipsum...

Check Your Understanding
------------------------

Lorem ipsum...

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

