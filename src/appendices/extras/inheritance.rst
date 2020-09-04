.. _class-inheritance:

Inheritance (Part 1)
====================

Throughout this textbook, we try to follow the simple goal of *Don't Repeat
Yourself* (DRY). Loops, functions, modules, objects, etc. allow us to create
and then reuse blocks of code. Classes are no different.

Imagine we have two objects that are very similar but not *quite* the same. One
example would be an electric car compared to one that runs on gasoline. Both
are "cars", and they share a number of properties and behaviors. However, there
are definite differences between the two.

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
            self.charge_level = 100  # Begin with 100% charge.

         def honk_horn(self):
            return "Beep!"

         def recharge(self):
            # Code for recharging the battery.

         def drive(self):
            # Code for decreasing energy_level after moving.

      class GasCar:
         def __init__(self, make, model, year, color, tank_size):
            self.make = make
            self.model = model
            self.year = year
            self.color = color
            self.tank_size = tank_size
            self.fuel_level = tank_size   # Begin with a full tank.

         def honk_horn(self):
            return "Beep!"

         def refuel(self):
            # Code for refilling the gas tank.

         def drive(self):
            # Code for decreasing fuel_level after moving.

.. index:: ! inheritance, ! parent class, ! child class, ! subclass

**Inheritance** refers to one class taking the same properties and methods from
a different one. In the example above, the two classes share the ``make``,
``model``, ``year``, and ``color`` property names. The classes also share the
same code for the ``honk_horn`` method.

Instead of repeating statements, we define a **parent class** to hold all of
the shared code. Next, we add **child classes**, which will *inherit* the
shared code. Finally, we add new properties and methods to the child classes.
This makes them distinct from each other, but they are both *related* to the
parent.

Let's work through an example.

Define a Parent Class
---------------------

First, we want to define the parent class called ``Car``. It holds the
properties and one method that ``EVCar`` and ``GasCar`` share.

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

Let's start with ``EVCar``, and for now we will only add one new method:

.. admonition:: Example

   The following program creates one ``Car`` object and one ``EVCar`` object.

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

      class EVCar(Car):
         def recharge(self):
            # Code for recharging the battery.
            return "Fully charged!"

      def main():
         my_car = Car('Ford', 'Focus', 2014, 'white')
         dream_car = EVCar('Tesla', 'Model S', 2020, 'Blue')

         print(type(my_car), type(dream_car))
         print(my_car.make, my_car.honk_horn())
         print(dream_car.make, dream_car.honk_horn())

         print(dream_car.recharge())
         print(my_car.recharge())

      if __name__ == '__main__':
         main()

   **Console Output**

   ::

      <class '__main__.Car'> <class '__main__.EVCar'>
      Ford Beep!
      Tesla Beep!
      Fully charged!
      File "main.py", line 25, in main
         print(my_car.recharge())
      AttributeError: 'Car' object has no attribute 'recharge'

#. Lines X and Y call the two classes and create the ``Car`` and ``EVCar``
   objects.
#. Line Z shows us that ``my_car`` and ``dream_car`` are different data types.
#. Line Z+1 prints the make and calls the ``honk_horn`` method for the ``Car``
   object.
#. Line Z+2 shows us that properties were assigned to the ``EVCar`` object.
   ``dream_car`` can also call the ``Car`` method ``honk_horn``!
#. Lines Z+4/5 shows us that ``dream_car`` can call the ``EVCar`` method
   ``recharge``, but ``my_car`` cannot.

This is what inheritance does! It allows a subclass to use the ``__init__`` and
other methods defined in the parent class.

.. admonition:: Try It!

   Add the ``GasCar`` child class to the program.

   .. todo:: Insert interactive editor here (Inheritance, part 1).

   Lorem ipsum...

Similar, but Different
----------------------

Notice that an ``EVCar`` and ``Car`` objects need to include properties that
are NOT defined in the ``Car`` class---``battery_size``, ``charge_level``,
``tank_size``, and ``fuel_level``.

On the next page, we will learn how to add new properties to a child class.
