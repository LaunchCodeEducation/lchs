.. _classes-and-objects-exercises:

Exercises: Classes and Objects
==============================

In these exercises, you will create a ``Robot`` class and use it to create
four ``Robot`` objects. You will also practice writing functions that display
information about the objects and race them against each other.

.. admonition:: Note

   If your teacher added you to a :ref:`Trinket course <trinket-course-assignments>`, login to your
   account to access the starter code for each exercise.

   Otherwise, use the links below to copy the starter code.

   #. `Trinket starter code <https://trinket.io/python/b3c2b6e9ff>`__ (*Remix*
      before getting started).
   #. `Repl.it starter code <https://repl.it/@launchcode/LCHS-Classes-Exercises>`__
      (*Fork* before getting started).

.. _chp13partNewClass:

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
#. Add one more property called ``distance``. This will not need a parameter
   in the ``__init__`` definition. Instead, every new ``Robot`` object will
   start with a ``distance`` value of ``0``.

.. admonition:: Tip

   Before you move on, test your new class!
   
   In ``main()``:

   a. Call the ``Robot`` class to create a new object. Assign it to a
      variable.
   b. Use dot notation to ``print`` the values for each property.
   c. To check the default, call the class at least once WITHOUT including an
      argument for ``year``.

Add Methods to ``Robot``
^^^^^^^^^^^^^^^^^^^^^^^^

#. Below ``__init__``, define a second method called ``move()``. This method
   should:

   #. Only take the ``self`` parameter.
   #. Generate a random number of steps (1 - 10) for the object to take. The
      range should include ``1`` and ``10`` as options. *Hint*: The ``randint``
      function is described in the :ref:`Random Module <pick-random-number>`
      section.
   #. Increase the ``distance`` property by the number of steps.
   #. Return the random number of steps.

#. Add the ``__str__`` method to return a string of the object properties.
   ``print(robot_name)`` should produce something like:

   ::

      Robot information:
        Name: Bob
        Mass: 25 kg
        Year made: 2020
        Distance traveled: 0

.. admonition:: Tip

   Test your methods!
   
   In ``main()``:

   a. ``print`` the ``Robot`` object to check the output.
   b. Use a loop to call the ``move()`` method several times. Inside the loop,
      ``print`` the steps taken and the updated ``robot_name.distance`` value. 

:ref:`Check your solutions <chp13part1>`.

.. _chp13partCreateObjects:

Part 2: Create Objects
----------------------

In part 1, you defined a class and created one ``Robot`` object in ``main()``.
Now create three more objects:

#. Assign each ``Robot`` object to its own variable.
#. Each object should have a different ``name`` value.
#. Use a mass value from ``25`` to ``40``. (*Bonus*: Use ``randint`` to
   generate the mass value instead of hard-coding a number when you call the
   class).

You now have 4 total robots. Add another statement in ``main()`` where you
place the objects inside a list. Assign the collection to a variable called
``robots``.

Update Distances
^^^^^^^^^^^^^^^^

Use a loop to iterate through the ``robots`` list. For each object, assign a
random value to the ``distance`` property, from ``1000`` to ``3000`` steps.

:ref:`Check your solutions <chp13part2>`.

.. _chp13partFindOldest:

Part 3: Find Oldest Robot
-------------------------

Between the class and ``main()``, define a function called ``oldest_robot``. It
should:

#. Accept a list of robots as a parameter.
#. Use a loop to iterate through the list.
#. Return the index value for the oldest robot in the list. *Caution*: A robot
   made in 2020 is NOT older than one made in 2019!
#. If two robots have the same ``year`` value, then the one with the largest
   ``distance`` will be older.

.. admonition:: Note

   The instructions assume that the list contains only one oldest robot. What
   if two old robots have the same ``year`` and ``distance`` values?

   We won't solve this problem here. However, add comments in your code
   describing how you would deal with multiple robots that are the same age.

In ``main()``, call the ``oldest_robot`` function and use ``robots`` for the
argument. Assign the returned index to a new variable.

Print out a message describing the result:

::

   "___ is the oldest robot (made in ___, ___ steps)."

Fill in the blanks with the name of the robot, the year it was made, and its
current number of steps.

:ref:`Check your solutions <chp13part3>`.

.. _chp13partRobotRaces:

Part 4: Robot Races
-------------------

Now it's time for the robots to compete against each other! Define the
``robot_race`` function that takes a list of robots as a parameter.

Within the function:

#. Each robot takes a turn running a race.
#. A robot runs the race by calling its ``move()`` method several times.
#. A robot is done with the race when it moves 30 steps or more.
#. Create a new list to store how many turns it takes each robot to complete
   the race. Use the string: ``'____ took ____ turns to take 30 steps.'``
   Fill in the blanks with the robot’s name and race result.
#. Return the list from the function.
#. Print the results to the console (one robot per line).

   ::

      Bob took 7 turns to take 30 steps.
      Jen took 5 turns to take 30 steps.
      Sal took 7 turns to take 30 steps.
      Jessi took 6 turns to take 30 steps.

*HINT*: There are a lot of different ways to approach this problem. One way
that works well is to count how many times ``move()`` gets called in order to
reach 30 steps.

:ref:`Check your solutions <chp13part4>`.