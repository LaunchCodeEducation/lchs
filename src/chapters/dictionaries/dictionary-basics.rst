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
#. Dictionaries store as many key/value pairs as needed, and each value needs
   a key. Without a key, the value cannot be accessed or modified.
#. The values in a dictionary may be of any data type, including lists and
   other dictionaries.
#. The keys should be an ``int`` or ``str`` data type. In most cases, using
   strings is the better choice. We will see why soon.

.. figure:: figures/dictionary.png
   :alt: Image showing the relationship of key/value pairs inside a dictionary.
   :width: 80%

   Dictionaries store data as key/value pairs.

Create a New Dictionary
-----------------------

To define a new dictionary, we need three things: a name, a set of keys, and
their corresponding values. There are several ways to do this, but the simplest
is to wrap the key/value pairs in curly braces ``{}``, with each pair
separated from the others by commas.

.. admonition:: Example

   .. sourcecode:: Python

      student = {'name' : 'Maria', 'id_number' : 1234, 'scores' : [90, 95, 88]}

*Note the following*:

#. The new dictionary is assigned to the variable ``student``.
#. Inside the curly braces, colons separate the key/value pairs, with the keys
   on the left and the values on the right.
   
   ``key : value``

#. In this example, all of the key names are strings---``'name', 'id_number',
   'scores'``. The values linked to these keys include a string, an integer,
   and a list.
#. To help make our code more readable, we can place each key/value pair on
   its own line.

   .. sourcecode:: Python
      :linenos:

      student = {
         'name' : 'Maria',
         'id_number' : 1234,
         'scores' : [90, 95, 88]
      }

   .. admonition:: Warning

      When putting the key/value pairs on separate lines, pay attention to spaces
      and tabs! Incorrect indentation can result in a bug.

#. We can also define an empty dictionary using just a pair of braces.

   .. sourcecode:: Python

      empty_dictionary = {}

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

   student['name']     # Access the value linked to the key 'name'.

.. admonition:: Try It!

   Experiment with the dictionary syntax to add or print values from
   different dictionaries.

   #. Run the code as-is to see the output.
   #. Note that line 9 prints the entire dictionary (with braces) to the
      console.
   #. Change the key in line 10 to print different values from ``student``.
   #. Add at least two key/value pairs to ``animal_info``, then add brackets
      in line 12 to print each of the new values.
   
   .. raw:: html

      <iframe src="https://trinket.io/embed/python3/5379d382bc?runOption=run" width="100%" height="350" frameborder="1" marginwidth="0" marginheight="0" allowfullscreen></iframe>


   Next:

   #. In line 10, try using a key name that does NOT exist in ``student``.
      What happens?
   #. Can we give two keys in the ``animal_info`` dictionary the same name? Try it and find out.
   #. Can we assign the same value (like ``5``) to two different keys in the
      same dictionary? Try it and find out.

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

