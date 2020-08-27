More Object Details
===================

Objects allow us to collect related data and actions into one place. So far,
we have printed the values of properties one at a time using dot notation. What
if we try to print the object itself?

Printing Objects
----------------

The following code defines a ``Dog`` class with a small number of properties
and methods.

.. admonition:: Try It!

   Run the program to see how the ``print`` function displays the ``dog_1`` and
   ``dog_2`` objects.

   .. raw:: html

      <iframe height="700px" width="100%" src="https://repl.it/@launchcode/Python-sandbox?lite=true" scrolling="no" frameborder="yes" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

Instead of giving us the information stored in each object, we see an output
similar to ``<__main__.Dog object at 0x7fe9867854f0>``. Despite the weird look,
this actually gives us some information:

#. The data type (an ``object`` of type ``Dog``).
#. A memory address, ``0x7fe9867854f0``, which differs between the two objects.

Usually, this format is NOT what we want to see when we print an object.
Fortunately, Python allows us to decide what an object should look like when it
gets printed.

The ``__str__`` Method
^^^^^^^^^^^^^^^^^^^^^^

.. index:: ! __str__

Every Python class includes a special method called ``__str__``. Notice that it
uses the same naming convention as the initializer: two underscores before and
after the name.

The ``__str__`` method is responsible for returning a string designed by the
programmer. This means that *we* get to choose what gets displayed when we
print our ``Dog`` objects.

In this case, let's format a string that includes the name and age of our pet.
Copy and paste this code into the editor above, making sure to indent each line
by the proper amount. Run the program to see the new output.

.. sourcecode:: python
   :lineno-start: 10

   def __str__(self):
      output = "Name of dog: {0}, Age of dog: {1} years"
      return output.format(self.name, self.age)

Note that the ``__str__`` method MUST create and return a string.

.. admonition:: Try It!

   Create your own return string in the ``__str__`` method. Feel free to
   include the ``is_cute`` value, or add and display new properties to the
   class.

Iterating Over Objects
----------------------

Lorem ipsum...

Cloning Objects
---------------

obj_a = obj_b?

Check Your Understanding
------------------------

Lorem ipsum...
