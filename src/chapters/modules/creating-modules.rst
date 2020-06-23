Creating Modules
================

Up until now, we have imported modules that are already part of the Python
libraries. Now let's look at how to define our own modules and save them
in a form we can use in other programs.

Create a New Python File
------------------------

The first step in making a module is to decide which values and functions
belong in that module. These should all perform similar tasks and/or be related
to each other in some way.

For example, let's assume we create a module called ``turtle_shapes``.
Functions like ``draw_square``, ``draw_polygon``, and ``draw_sprite`` would be
good choices to put in the module, but something like
``calculate_average_grade`` definitely does NOT belong.

The next step is to open a new file in our code editor and give it a name that:

#. begins with a letter,
#. contains only lowercase letters,
#. is as short as possible but still descriptive,
#. separates words with an underscore ``_``,
#. ends with the extension ``.py`` (for example, ``turtle_shapes.py``).

.. admonition:: Note

   The ``.py`` extension tells a code editor that the contents of the file
   follow the Python programming syntax.

Finally, we add the functions and values we want in the module. We code these
just like any other program.

That's pretty much it. Once we save the file, we can import the entire module
or specific functions into another program with the syntax we learned:

.. sourcecode:: Python

   import turtle_shapes
   from turtle_shapes import draw_polygon

Note that we do NOT need to include the ``.py`` extension when we import the
module.

Let's build a module to practice this process.

Separating Turtle Properties
----------------------------

You probably noticed that every time we use a turtle in an example or exercise,
we include a set of statements that define properties for the turtle:

.. admonition:: Example

   Count the number of "prep" steps we need before our turtle draws its first
   line:

   .. sourcecode:: Python
      :linenos:

      import turtle

      bob = turtle.Turtle()
      bob.color('blue')
      bob.shape('turtle')
      bob.pensize(3)
      bob.speed(8)

      bob.circle(75)

   Line 3 creates the new turtle object, called ``bob``. Lines 4 - 7 set the
   properties, and line 8 finally draws something on the screen.

It takes one line of code to set each of the properties for a turtle. If we
need to define multiple turtles, this gets tedious really fast.

We can help ourselves by moving the setup code into a pair of functions, and
then calling those functions for each new turtle:

.. admonition:: Example

   By including some default values, we can call the ``set_turtle_properties``
   function with just a turtle name, the name and some of the properties, or
   with arguments for each property.

   .. sourcecode:: Python
      :linenos:

      import turtle

      def set_turtle_properties(turtle_name, t_color='black', t_shape='turtle', t_pen=3, t_speed=8):
         turtle_name.color(t_color)
         turtle_name.shape(t_shape)
         turtle_name.pensize(t_pen)
         turtle_name.speed(t_speed)

      bob = turtle.Turtle()
      lin = turtle.Turtle()
      set_turtle_properties(bob)
      set_turtle_properties(lin, 'purple', 'square')

This is better, since it reduces the repetition in the program. However, if we
want to use this shortcut in ALL of our turtle programs, we need to create a
module to hold the code.

Create the ``turtle_prep`` File
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Lorem ipsum...

File Locations
--------------

Lorem ipsum...
