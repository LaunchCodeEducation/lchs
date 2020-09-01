.. _class-inheritance:

Inheritance
===========

Throughout the textbook, we try to follow the simple goal of *Don't Repeat
Yourself* (DRY). Loops, functions, modules, objects, etc. allow us to create
and then reuse blocks of code. Classes are no different.

Imagine we have two objects that are very similar but not *quite* the same,
like an electric car vs. one that runs on gasoline. Both are technically
"cars", and they share a number of properties and behaviors. However, there are
definite differences between the two.

We could code separate ``EVCar`` and ``GasCar`` classes, but notice how each
one repeats some of the same code:

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      class EVCar:
         def __init__(self, make, model, year, color, battery_size):
            self.make = make
            self.model = model
            self.year = year
            self.color = color
            self.battery_size = battery_size

         def honk_horn(self):
            return "Beep!"

         def refuel(self):
            # Code for recharging the battery...

         def charge_left(self):
            # Code to return current charge remaining...

      class GasCar:
         def __init__(self, make, model, year, color, tank_size):
            self.make = make
            self.model = model
            self.year = year
            self.color = color
            self.tank_size = tank_size

         def honk_horn(self):
            return "Beep!"

         def refuel(self):
            # Code for refilling the gas tank...

         def fuel_left(self):
            # Code to return current gas remaining...

.. index:: ! inheritance, ! parent class, ! child class, ! subclass

**Inheritance** refers to one class taking the same properties and methods from
a different one. In the example above, the two classes have the same ``make``,
``model``, and ``year`` properties. The classes also share the same code for
the ``honk_horn`` method.

Instead of repeating statements, we define a **parent class** to hold all of
the shared code. Next, we add **child classes**, which will *inherit* the
shared code. Finally, we add new properties and methods to the child classes.
This makes them distinct from each other, but each one is still *related* to
the parent.

Let's work through an example.

Define a Parent Class
---------------------

First we want to define the parent class called ``Car``. It will hold the
properties and the one method that ``EVCar`` and ``GasCar`` share.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      class Car:
         def __init__(self, make, model, year, color):
            self.make = make
            self.model = model
            self.year = year
            self.color = color

         def honk_horn(self):
            return "Beep!"

The ``Car`` class is fully functional, and we can use it to create multiple
``Car`` objects with different makes, models, years, and colors.

Define a Child Class
--------------------

.. index:: ! subclass

Now let's add a child class (also called a **subclass**) that inherits the code
contained in ``Car``.

The general syntax to define a child class is:

.. sourcecode:: python

   class ChildClassName(ParentClassName):

By placing ``ParentClassName`` inside the parentheses ``()`` we link
``ChildClassName`` to all of the code the parent contains.

Lorem ipsum...
