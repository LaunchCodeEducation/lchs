Working With Objects
====================

Once created, objects are *mutable*. We can change the values of properties or
add new ones as needed.

Object Properties
-----------------

When using objects, we often want to access the value of a property, change a
property value, or add a completely new property. To do this, we need the
object's name as well as the name of the property.

To modify object properties, we use *dot notation*:

.. sourcecode:: python

   object_name.property_name  # Access & return a property value from object_name.

   object_name.property_name = new_value  # Change the value of an existing property.

   object_name.new_property = value   # Add a new property and value to the object.

Note tha ``property_name`` and ``new_property`` do NOT end with a set of
parentheses ``()``.

.. admonition:: Try It!

   In the program below, ``dog`` is an object with two properties---``name``
   and ``age``. Follow the instructions below the editor to practice using dot
   notation with an object.

   .. raw:: html

      <iframe src="https://trinket.io/embed/python/0b67de0e64" width="100%" height="450" frameborder="1" marginwidth="0" marginheight="0" allowfullscreen></iframe>

   #. Run the program as-is to see how the dot notation on lines 8 and 10
      accesses and *returns* the property values.
   #. On line 13, use dot notation to change the value of the ``name``
      property to ``'Fleas'``.
   #. On line 14, use the ``+=`` operator to increase the age of ``dog`` by 3
      years.
   #. Run the program again. Properly done, the output should look like:

      ::

         Spot
         3
         Fleas 6

   #. Uncomment line 19 and run the program. You should see an error message
      because ``dog`` does not contain a property called ``breed``.
   #. On the line 17, use dot notation to create a new property called
      ``breed`` and assign it a string value.
   #. On line 18, add the ``is_cute`` property to ``dog``. Assign it a boolean
      value instead of a string.
   #. Run the program again. Properly done, the output should look similar to:

      ::

         Spot
         3
         Fleas 6
         mutt True

Calling Methods
---------------

When we learned about strings, lists, and dictionaries, we practiced calling
methods on each type of object. The same syntax applies for all other objects
as well:

.. sourcecode:: python

   object_name.method_name(arguments)

Note that some methods require *arguments* (data) inside the parentheses
``()``, while other methods do not.

.. sourcecode:: python

   my_list.append(100)  # 100 is the argument for the list method .append()

   my_string.lower() # The string method .lower() requires no arguments

Methods vs. Functions
^^^^^^^^^^^^^^^^^^^^^

Lorem ipsum...

Check Your Understanding
------------------------

Lorem ipsum...
