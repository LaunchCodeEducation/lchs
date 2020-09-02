Exercises: Classes and Objects
==============================

In these exercises, you will create a ``Robot`` class and use it to create
four ``Robot`` objects. You will also practice writing functions that display
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
   c. To check the default, call the class at least once WITHOUT including an
      argument for ``year``.

Add Methods to ``Robot``
^^^^^^^^^^^^^^^^^^^^^^^^

#. Below ``__init__``, define a second method called ``move()``. This method
   should:

   #. Only take the ``self`` parameter.
   #. Generate a random number of steps (1 - 10) for the object to take. The
      range should include ``1`` and ``10`` as options. *Hint*: The ``randint``
      function is described in the
      :ref:`The random Module <pick-random-number>` section.
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

Part 2: Create Objects
----------------------

In part 1, you defined a class and created one ``Robot`` object. In ``main()``
create three more objects:

#. Assign each ``Robot`` object to its own variable.
#. Each object should have a different ``name`` value.
#. Use a randomly generated mass for each new robot. The masses should be in
   the range from ``25`` to ``40``.

You now have 4 total robots. Place their variables inside a list, and assign
the collection to a variable called ``robots``.

Part 3: Find Oldest Robot
-------------------------

Outside of the class, define a function called ``oldest_robot``. It should:

#. Accept a list as a parameter.
#. Use a loop to iterate through the list.
#. Check to see if each element in the list is a ``Robot`` data type. If not,
   return the error message, ``"Invalid data type. Robot objects required."``
#. Check the ``year`` value for all of the robots.
#. Return the *index value* for the oldest robot in the list. *Caution*:
   Remember that a robot made in 2020 is NOT older than one made in 2019!

.. admonition:: Note

   The instructions assume that there will only be ONE "oldest" robot in your
   list. What if two or more objects have the same ``year`` value?

   We won't solve this issue here. However, add comments in your code
   describing how you would deal with multiple robots that are the same age.

In ``main()`` call the ``oldest_robot`` function and use ``robots`` for the
argument. Assign the returned index to a new variable.

Print out a message describing the result:

::

   Of the ___ robots, ___ is the oldest.

Fill in the blanks with the length of the ``robots`` list and the ``name`` of
the oldest robot.

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
