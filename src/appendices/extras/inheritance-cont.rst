Inheritance (Part 2)
====================

Add New Properties to Child Class
---------------------------------

An ``EVCar`` object needs two properties that are not defined in the ``Car``
class: ``battery_size`` and ``charge_level``.

To include these, we must define an ``__init__`` method inside the ``EVCar``
class. The idea is to inherit all of the property names from the ``Car`` class
and just add the two new ones. 

The general syntax for this is:

.. sourcecode:: python
   :linenos:

   class ChildClassName(ParentClassName):

      def __init__(self, parent_properties, new_property):
         # First, set the properties found in ParentClassName.
         ParentClassName.__init__(self, parent_properties)
         # Next, assign a value to the new property.
         self.new_property = new_property

When we call the child class, the ``__init__`` method runs in two parts. First,
it calls the parent class and completes that initialization. Next, control
returns to the ``__init__`` method in the child class, and values are assigned
to any additional properties.

#. Line 3 defines the initializer method for the child class. Note that the
   parameters include ``self`` and variables for both the parent and child
   properties.
#. Line 5 calls the ``__init__`` method from the parent class. This assigns
   values to all properties inherited from that class.
#. Line 7 creates a new property name and assigns it a value.

.. admonition:: Example

   Let's see how this works for our ``EVCar`` class:

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
         def __init__(self, make, model, year, color, battery_size):
            Car.__init__(self, make, model, year, color)
            self.battery_size = battery_size
            self.charge_level = 100  # Begin with 100% charge.

         def recharge(self):
            # Code for recharging the battery.
            return "Fully charged!"

      def main():
         my_car = Car('Saturn', 'SW-1', 1999, 'green')
         dream_car = EVCar('Tesla', 'Model S', 2020, 'blue', '100 kWh')

         print("my_car:", vars(my_car))
         print("dream_car:", vars(dream_car))

      if __name__ == '__main__':
         main()

   **Console Output**

   ::

      my_car: {'make': 'Saturn', 'model': 'SW-1', 'year': 1999, 'color': 'green'}
      dream_car: {'make': 'Tesla', 'model': 'Model S', 'year': 2020, 'color': 'blue', 'battery_size': '100 kWh', 'charge_level': 100}

   Lines 25 and 26 print out the property names and values for the ``Car`` and
   ``EVCar`` objects. Note that ``dream_car`` includes two properties that are
   missing from ``my_car``.

Change Existing Methods
-----------------------

Lorem ipsum...

.. index:: ! overriding methods

Definition of **overriding** (parent and child class contain methods with
the same name)...

Try It!
-------

Lorem ipsum...
