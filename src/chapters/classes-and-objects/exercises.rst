Exercises: Classes and Objects
==============================

In these exercises, you will create a ``Robot`` class and use it to create
five ``Robot`` objects. You will also practice writing functions that display
information about the objects as well as race them against each other.

.. admonition:: Note

   If your teacher added you to a :ref:`repl.it classroom <replit-classroom-assignments>`
   or a :ref:`Trinket course <trinket-course-assignments>`, login to your
   account to access the starter code for each exercise.

   If you are NOT enrolled in a repl.it classroom or Trinket course, use the
   links below to complete the project.

.. todo:: Insert repl.it and Trinket links to the starter code (Classes exercises).

Part 1: Create a New Class
--------------------------

Open up the starter code and notice that it imports the ``random`` module.
Below the ``import`` statement, define the ``Robot`` class.

Add Properties to ``Robot``
^^^^^^^^^^^^^^^^^^^^^^^^^^^

#. Inside the class, define the ``__init__`` method. It should include
   parameters for ``self``, ``name``, ``mass``, and ``year``.
#. Give a default value to ``year``.
#. Assign the property values as described in the
   :ref:`Setting Property Values <set-property-values>` section.
#. Add one more property called ``distance``. This will NOT have a
   parameter, and every new ``Robot`` object will start with a ``distance``
   value of ``0``.

.. admonition:: Tip

   Before you move on, test your new class!
   
   In ``main()``:

   a. Call the ``Robot`` class to create a new object. Assign it to a
      variable.
   b. Use dot notation to ``print`` the values for each property.

Add Methods to ``Robot``
^^^^^^^^^^^^^^^^^^^^^^^^

#. Below the ``__init__`` method, define a method called ``move()``. The method
   should:

   #. Only take the ``self`` parameter.
   #. Generate a random number of steps (1 - 10) for the object to take. The
      range should include ``1`` and ``10``. *Hint*: The ``randint`` function
      is described in the :ref:`The random Module <pick-random-number>`
      section.
   #. Increase the ``distance`` property by the number of steps.
   #. Return the random number of steps.

#. Add the ``__str__`` method to return a string of the object properties.
   ``print(robot_name)`` should produce something similar to:

   ::

      Robot information:
        Name: Bob
        Mass: 25 kg
        Year made: 2019
        Distance traveled: 0

.. admonition:: Tip

   Test your methods!
   
   In ``main()``:

   a. ``print`` the ``Robot`` object to check the output.
   b. Use a loop to call the ``move()`` method several times. Inside the loop,
      ``print`` the steps taken and the updated ``robot_name.distance`` value. 

Part 2: Create Objects
----------------------

Lorem ipsum...

Store objects in a list...

Part 3: Print Robot Info
------------------------

Function to print "Lorem ipsum..."

Can EITHER do this inside the function with ``.format()`` and dot notation OR
by adding a ``__str__`` method to the class.

List of robots as the parameter...

Part 4: Robot Races
-------------------

Now it's time to let the robots compete against each other! Define a
``robot_race`` function that takes a list as a parameter.

Within the function, race the five robots together by using the ``move``
method. A machine is done with the race when they reach 20 steps or more.
Store the result as a string: ``'____ took ____ turns to take 20 steps.'``
Fill in the blanks with the robot’s name and race result. Create a new list
to store how many turns it takes each robot to complete the race.

Return the list from the function, then print the results to the console (one
robot per line).

*HINT*: There are a lot of different ways to approach this problem. One way
that works well is to see how many iterations of the ``move`` method it will
take for each animal to reach 20 steps.
