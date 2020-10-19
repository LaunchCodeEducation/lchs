Project: Local Turtle Races
===========================

Hopefully, by the end of this project you will have a program that you just
can't resist running over and over again.

[GIF of turtle races]

Open Visual Studio Code and create a new project directory and a
``turtle_race.py`` file.

Part A: Drawing Space Setup
---------------------------

#. In ``turtle_race.py``, import the ``turtle`` and ``random`` modules.
#. Define a ``main()`` function. Add statements to create a new ``Screen()``
   object. Call methods on the object to give the window a title and a size of
   600 x 600 pixels.
#. End ``main()`` by calling the ``.exitonclick()`` method on the object.

Run your program to test your window features.

Part B: Create Turtles
----------------------

Define a function called ``create_racing_turtle()`` that:

#. Takes two parameters, one for color and one for shape. Include the default
   values of ``'black'`` and ``'turtle'`` for these variables.
#. Creates a new turtle object and assigns it the color and shape values.
#. Assigns every turtle the same ``pensize`` and ``speed`` (``3`` and ``8`` are
   good choices).
#. Returns the new turtle object.

In ``main()``, call the ``create_racing_turtle`` function and assign the
returned object to a variable. Verify that the function works by drawing a
single line with ``variable_name.forward(100)``.

Once the function works, use it to create at least 4 turtle objects. Put each
of these into a list called ``racers``.

Part C: Start & Finish Lines
----------------------------

Now that you've created some racing turtles, you need to draw the finish line
and put the objects at their starting positions. The participants will race
across a straight track that is 400 pixels long. The first turtle to the finish
line wins!

Draw the Finish Line
^^^^^^^^^^^^^^^^^^^^

To mark the finish line on your racetrack, you will use an *invisible* turtle
to draw that line.

.. admonition:: Note

   Some of the methods on this page may be unfamiliar to you. That's OK. We
   provide a summary for how to use each one, and you can always check the
   `Python documentation <https://docs.python.org/3/library/turtle.html>`__ for
   more details.

Define a function called ``draw_finish()`` that:

#. Takes the length of the ``racers`` list as the parameter.
#. Creates a new ``Turtle`` object and assigns it to a variable.
#. Calls the ``.hideturtle()`` method on the object. Its lines will still show
   up in the drawing space, but the turtle shape will remain invisible. The
   method requires no arguments inside the parentheses ``()``.
#. Sets the ``pensize`` to ``6`` and the ``speed`` to ``0``.
#. Uses the ``penup``, ``pendown`` and movement methods to move the turtle
   forward 200 pixels and then draw a vertical line up towards the top of the
   screen. The length of the line should depend on how many turtles are in the
   ``racers`` list.

   .. list-table:: Finish Line Length
      :widths: auto
      :header-rows: 1

      * - Number of Turtle Racers
        - Length in Pixels
      * - 2
        - 50
      * - 3
        - 100
      * - 4
        - 150
      * - 5
        - 200

#. ``draw_finish`` does not return any value.

In ``main()``, call ``draw_finish`` several times, using different integers for
the argument.

Place Racers at Start
^^^^^^^^^^^^^^^^^^^^^

With 4 racing turtles, the starting lineup should look something like this:

[IMAGE - turtle racers on the starting blocks]

Caption - Turtle shapes and colors may vary.

By default, all new ``Turtle`` objects are placed in the center of the drawing
space, which has the coordinates ``(0, 0)``. This means each new turtle gets
stacked on top of all the others. We need to spread them out before they can
race!

Define a function called ``start_positions`` that:

#. Takes the ``racers`` list as a parameter.
#. Uses a loop to iterate through the list. For each turtle object:

   a. Call the ``penup`` method.
   b. Use the ``.goto(x_value, y_value)`` method to place the turtle at its
      starting point. ``goto()`` places the turtle at a specific spot on the
      screen. ``x_value`` represents the left-right position, and each turtle
      will use ``-200`` for this. ``-200`` moves the turtle backwards 200
      pixels from the starting point of ``(0, 0)``.
      
      ``y_value`` represents the up-down position. The first turtle in the list
      will have a ``y_value`` of ``0``. The second will be ``50``. The third
      ``100``, etc.
   c. Call the ``pendown`` method. The turtle is ready to go!

#. ``start_positions`` does not return any value.

In ``main()``, call ``start_positions`` several times, placing two or more
turtles in the ``racers`` list. No matter how many objects are in ``racers``,
the start and finish lines should always match in length.

.. admonition:: Tip

   Use variables to calculate ``y_value`` instead of typing in specific
   numbers! *Hint*: Maybe you can relate ``y_value`` to an ``index`` in the
   ``racers`` list... 

Part D: Racing Loop
-------------------

Lorem ipsum...

Part E: Sanity Check
--------------------

Lorem ipsum...

Bonus Mission
-------------

Replay option...
