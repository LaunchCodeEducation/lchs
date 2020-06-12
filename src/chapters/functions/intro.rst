Introduction
============

Recall how we used a turtle object to draw a square:

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      import turtle

      bob = turtle.Turtle()

      side_length = 75
      for side in range(4):
         bob.forward(side_length)
         bob.left(90)

   To draw a square, we need to create a turtle and specify the length of one 
   side. The ``for`` loop runs, and our turtle does its job.

   .. figure:: figures/turtle-square.gif
      :alt: A gif showing a Python turtle drawing a square.

What if we have several different turtles on the screen, and we want each one
to draw a square? We could copy and paste the ``for`` loop once for each
turtle, but we would need to change the ``forward`` and ``left`` statements to
match each of the turtle names.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      import turtle

      bob = turtle.Turtle()
      wonder = turtle.Turtle()
      im_really_a_tortoise = turtle.Turtle()

      # Turtle color, shape, speed, and location code...

      side_length = 50
      for side in range(4):
         bob.forward(side_length)
         bob.left(90)

      side_length = 75
      for side in range(4):
         wonder.forward(side_length)
         wonder.left(90)

      side_length = 100
      for side in range(4):
         im_really_a_tortoise.forward(side_length)
         im_really_a_tortoise.left(90)

   .. figure:: figures/3-turtle-squares.gif
      :alt: A gif showing a three Python turtles drawing one square each.

This is inefficient! Rather than having to copy, paste, and then edit the loop,
it would be nice if we could use the SAME lines of code over and over again.

*Functions* allow us to do this!

What is a Function?
-------------------

.. index:: ! function

A **function** is a reusable piece of code, and it consists of a series of
statements that belong together. Like variables, we assign functions
names. By *calling* a function name, we tell Python to run that block of code
when we need it.

You used a function when you wrote your first Python program:

.. sourcecode:: Python

   print('Hello, World!')

To display information in the console, the ``print`` function follows a
detailed set of instructions to convert the values in the ``()`` to symbols on
the screen. We do not see these steps, but we execute them every time we use
the function.

For the three-turtle example above, imagine we create a function named
``draw_square``. We could put the ``for`` loop inside this function, and then
run the function once for each turtle. This allows us to use the same lines of
code for each turtle instead of copy/pasting multiple copies of the
instructions.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      import turtle

      bob = turtle.Turtle()
      wonder = turtle.Turtle()
      im_really_a_tortoise = turtle.Turtle()

      # Turtle color, shape, speed, and location code...

      draw_square(bob, 50)
      draw_square(wonder, 75)
      draw_square(im_really_a_tortoise, 100)
   
   Each time we run the ``draw_square`` function, we tell Python which turtle
   to use as well as the value for ``side_length``.

When you wrote your ``'Hello, World!'`` program, we skipped the full
explanation of how functions work. Now, you are ready to learn those details,
as well as how functions can be used and how to create your own.

Function Control Flow
---------------------

Lorem ipsum...

Check Your Understanding
------------------------

Lorem ipsum...
