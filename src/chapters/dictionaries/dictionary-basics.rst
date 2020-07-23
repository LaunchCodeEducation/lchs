Dictionary Basics
=================

We learned that both lists and strings are examples of *ordered collections*.
They are built from smaller, individual pieces of data, each of which has its
own index value.

.. index:: ! dictionary

A third type of Python collection is called a **dictionary**.

.. index:: ! key/value pair

**Key dictionary facts:**

#. Dictionaries are *unordered* collections. They do NOT use index values
   (0, 1, 2, ...) to organize the data from left to right.
#. Dictionaries are *mutable*. We can add, remove, or modify the data in the
   collection.
#. Dictionaries store data using sets of **key/value pairs**. Think of a *key*
   just like a label or a variable name. It *points to* a specific piece of
   data, called the *value*.
#. The values in a dictionary may be of any data type, including lists and other
   dictionaries.
#. The keys should either be an ``int`` or ``str`` data type. In most cases,
   using strings is the better choice. We will see why soon.

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

*Note the following*:

#. Inside the curly braces, colons separate the key/value pairs, with the keys
   on the left and the values on the right.
   
   ``key : value``

#. In this example, all of the key names are strings---``'name', 'id_number',
   'scores'``.
#. We can define an empty dictionary using a pair of braces.

To help make our code more readable, when we define a dictionary, place each
key/value pair on its own line.

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

With lists and strings, we access elements or characters by using bracket
notation and placing an index value inside the ``[]``.

.. sourcecode:: Python
   :linenos:

   my_list[0]     # Access the first element in my_list.
   my_string[3]   # Access the character at index 3 in my_string.

To access a specific entry in a dictionary, we still use bracket notation.
However, instead of placing an index inside the ``[]``, we use a key name
instead.

.. sourcecode:: Python
   :linenos:

   my_dictionary['name']     # Access the value linked to the key 'name'.

.. admonition:: Try It!

   Experiment with the dictionary syntax to add or print values from
   ``my_dictionary``.

   #. Run the code as-is to see the output.
   #. Note that line X prints the entire dictionary (with braces) to the
      console.
   #. Change the key in line Y to print different values from
      ``my_dictionary``.
   #. Add at least two new key/value pairs to ``other_dictionary``, then update
      line Z to print each of the new values.
   #. In line Z, try using a key name that does NOT exist in the dictionary.
   #. Can we give two keys in the same dictionary the same name? Try it and
      find out.
   #. Can we assign the same value (e.g. 5) to two different keys in the same
      dictionary? Try it and find out.

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

