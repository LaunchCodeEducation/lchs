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

Add Properties
^^^^^^^^^^^^^^

#. Inside the class, define the ``__init__`` method. It should include
   parameters for ``self``, ``name``, ``mass``, ``year``, and ``color``.
#. Give default values to ``year`` and ``color``.
#. Assign the property values as described in the
   :ref:`Setting Property Values <set-property-values>` section.
#. Before you move on, test your code!

   #. In ``main()`` call the ``Robot`` class to create a new object and assign
      it to a variable.
   #. Use dot notation to ``print`` the values for each property.

Add Methods
^^^^^^^^^^^

#. Below the ``__init__`` method, define a method called ``move()``. 
#. Give default values to ``year`` and ``color``.
#. Assign the property values as described in the
   :ref:`Setting Property Values <set-property-values>` section.
#. Before you move on, test your code!

   #. In ``main()`` call the ``Robot`` class to create a new object and assign
      it to a variable.
   #. Use dot notation to ``print`` the values for each property.

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
