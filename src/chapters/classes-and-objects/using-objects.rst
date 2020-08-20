Working With Objects
====================

Once created, objects are *mutable*. We can change the values of properties or
add new ones as needed.

Accessing Properties
--------------------

When using objects, we often want to access or change the value of one of the
properties. To do this, we will need the object's name and the name of the
property.

To access, change, or create a property, we use *dot notation*.

.. sourcecode:: python

   object_name.property_name  # Access a property value from the object.

   object_name.property_name = new_value  # Change the value of an existing property.

   object_name.new_property = value   # Add a new property and value to the object.

Note tha ``property_name`` and ``new_property`` do NOT end with a set of
parentheses ``()``.

.. admonition:: Try It!

   In the program below, ``dog`` is an object with two properties---``name``
   and ``age``. Follow the instructions below the editor to practice using dot
   notation with an object.

   .. todo:: Insert interactive editor here (object dot notation).

   #. Run the program as-is to see how the dot notation on lines X and Y
      *accesses* each property.
   #. On line Z, use dot notation to change the value of the ``name`` property.
   #. On line Z+1, use the ``+=`` operator to increase the age of ``dog`` by
      3 years.
   #. Run the program again. Properly done, the output should look like:

      ::

         Lore ipsum...

   #. Uncomment line A and run the program. You should see an error message
      because ``dog`` does not contain the properties ``breed`` or ``is_cute``.
   #. On the line before this ``print`` statement, use dot notation to create
      a new property called ``breed`` and assign it a string value.
   #. Repeat step 6 for the ``is_cute`` property, but assign it a boolean value
      instead of a string.
   #. Run the program again. Properly done, the output should look similar to:

      ::

         Lore ipsum...


Methods vs. Functions
---------------------

Lorem ipsum...

Dot Notation
^^^^^^^^^^^^

To access a property with dot notation, the code looks like: ``object.key``. Notice that the key is no longer surrounded by quotes. However, keys are still strings.

.. note::

   Recall, the only restraint in naming a key is that it has to be a valid JavaScript string.
   Since a key could potentially have a space in it, bracket syntax would be the only way to access the value in that property because of the quotes.

.. admonition:: Example

   .. sourcecode:: js
      :linenos:

      let tortoiseOne = {
          species: "Galapagos Tortoise",
          name: "Pete",
          weight: 919,
          age: 85,
          diet: ["pumpkins", "lettuce", "cabbage"]
      };

      console.log(tortoiseOne["name"]);
      console.log(tortoiseOne.name);

   **Console Output**

   ::

      Pete
      Pete

Modifying Properties
--------------------

A programmer can modify the value of a property by using either notation style.

.. warning::

   Recall that mutability means that a data structure can be modified without making a copy of that structure.
   Objects are mutable data structures.
   When you change the value of a property, the original object is modified and a copy is NOT made.

.. admonition:: Example

   In our zoo software, we may want to update Pete's weight as he has gained 10 lbs.
   We will use both bracket syntax and dot notation for our software, but that is not a requirement!
   Feel free to use whichever one suits your needs and is easiest for you and your colleagues to read.

   .. sourcecode:: js
      :linenos:

      let tortoiseOne = {
          species: "Galapagos Tortoise",
          name: "Pete",
          weight: 919,
          age: 85,
          diet: ["pumpkins", "lettuce", "cabbage"]
      };

      console.log(tortoiseOne.weight);

      newWeight = tortoiseOne.weight + 10;

      tortoiseOne["weight"] = newWeight;

      console.log(tortoiseOne["weight"]);

   **Console Output**

   ::

      919
      929

.. _add-new-object-properties:

Add New Key/Value Pairs
^^^^^^^^^^^^^^^^^^^^^^^^

After declaring and initializing an object, we can add new properties at any
time by using bracket syntax:

.. sourcecode:: js

   objectName["new-key"] = propertyValue;

.. admonition:: Example

   .. sourcecode:: js
      :linenos:

      let tortoiseTwo = {
          species: "Galapagos Tortoise",
          name: "Pete",
          weight: 919
      };

      console.log(tortoiseTwo);

      tortoiseTwo["age"] = 120;
      tortoiseTwo["speed"] = 'Faster than the hare.'

      console.log(tortoiseTwo);
      console.log(tortoiseTwo.age);

   **Console Output**

   ::

      { species: 'Galapagos Tortoise', name: 'Pete', weight: 919 }
      { species: 'Galapagos Tortoise',
         name: 'Pete',
         weight: 919,
         age: 120,
         speed: 'Faster than the hare.' }
      120

Check Your Understanding
------------------------

All of the questions below refer to an object called ``giraffe``.

.. sourcecode:: js
   :linenos:

   let giraffe = {
     species: "Reticulated Giraffe",
     name: "Cynthia",
     weight: 1500,
     age: 15,
     diet: "leaves"
   };

.. admonition:: Question

   We want to add a method after the ``diet`` property for easily increasing Cynthia's age on her birthday.
   Which of the following is missing from our method? You can select MORE than one.

   ``birthday: function () {age = age + 1;}``

   a. ``return``
   b. ``this``
   c. ``diet``
   d. a comma

.. admonition:: Question

   Could we use bracket syntax, dot notation, or both to access the properties of ``giraffe``?

