Search a Dictionary
===================

With both lists and strings, we used the ``in`` and ``not in`` operators to
search for specific values. These expressions returned either ``True`` or
``False`` depending on if the value was found in the collection.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      greeting = 'Hello, World!'
      fruits = ['apple', 'banana', 'pear', 'kiwi', 'orange']
      numbers = [28, 32, 7, 29, 33, 0]

      print('or' in greeting)  # Search for the substring 'or' in the larger string.
      print('nana' in fruits)  # Search for the value 'nana' in the list of strings.

      print('!' not in greeting) # Check if '!' is NOT in 'Hello, World!'.
      print(42 not in numbers)   # Check if 42 is NOT in the numbers list.

   **Console Output**

   ::

      True
      False
      False
      True

Since the elements in a dictionary come as pairs, we search for an item in
*either* the set of keys *or* the set of values.

We practiced with the ``keys()`` and ``values()`` methods in the previous two
sections, and we can use them in a similar way to search a dictionary.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      ticket_holders = {
         'Bob' : 100,
         'Jessi' : 103,
         'Maria' : 101,
         'Devon' : 102
      }

      print(101 in ticket_holders.keys())
      print(101 in ticket_holders.values())

      print('Jessi' in ticket_holders.keys())
      print('Jessi' in ticket_holders.values())

   **Console Output**

   ::

      False
      True
      True
      False

   #. In line 8, ``101 in ticket_holders.keys()`` returns ``False``. Even
      though ``101`` is in the dictionary, it is a *value*, and we are
      searching through the *keys*.
   #. In line 9, ``101 in ticket_holders.values()`` returns ``True``.
   #. In lines 10 and 11, we search for the string ``'Jessi'`` first in the
      keys and then in the values.

Default Search Method
---------------------

If we do not add the ``keys()`` or ``values()`` method after the dictionary
name, Python searches the *keys* by default.

This means that

.. sourcecode:: python

   search_value in dictionary_name.keys()

returns the same result as

.. sourcecode:: python

   search_value in dictionary_name

Try It!
-------

Lorem ipsum...

Check Your Understanding
------------------------

Lorem ipsum...
