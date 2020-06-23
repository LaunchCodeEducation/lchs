The ``random`` Module
=====================

We often want to use random numbers in programs. Here are a few typical uses:

#. To play a game where the computer needs to throw some dice, pick a number,
   or flip a coin.
#. To select a random item from a list.
#. To randomly choose an event to apply to a virtual city.
#. To encrypt your banking session on the Internet.

Python provides a module called ``random`` that helps with tasks like this.

Generate a Random Number
------------------------

Press the *Run* button a number of times for the program below. Note that the
values change each time. These are random numbers.

   [Insert interactive repl here.]

.. index:: ! random(), ! randint()

The **random()** function returns a float value in the range 0.0 - 1.0.
However, while 0.0 is possible 1.0 is not. If we need a larger float result,
say from 0.0 to 10.0, we simply multiply the result from ``random()`` by the
top value we want.

In the case shown below, we’ve converted the result from ``random()`` to a
number in the range 0.0 - 4.9999... Press the *Run* button several times to
confirm that values range between 0.0 up to but not including 5.0.

   [Insert interactive repl here.]

The **randint()** function is a useful modification of ``random()``. It
generates an integer between the two arguments, but in this case, the results
include both end points.

   [Insert interactive repl here.]

Not *Really* Random
^^^^^^^^^^^^^^^^^^^

It is important to note that random number generators are based on
*algorithms*. This means that the results are predictable and not truly random.

Each algorithm starts with a **seed value**, which the code uses to create a
result. Every time we ask for another random number, we get one based on the
current seed, and the value of the seed gets updated. If we figure out how the
seed values are generated, then we can predict what the next "random" result
will be.

The good news is that each time we run the program, the seed value is likely
to be different (for example, the number of seconds since midnight). This means
that even though the random numbers come from following an algorithm, we will
likely get random behavior each time we run our program.

.. admonition:: Note

   Theoretically, if you could figure out the algorithm and seed values for a
   lottery game, then you could always pick the winning numbers!

   Doing this would be really, really hard, however.

Select an Item from a Collection
--------------------------------

.. index:: ! choice()

Another useful function from the ``random`` module is the **choice()**
function. It selects a random item from a string, list, or other collection.

Run the following program several times to see how this works:

   [Insert interactive repl here.]

We could do the same thing with ``randint()`` and bracket notation, but the
``choice()`` function wraps this up into a simple shortcut.

.. sourcecode:: Python
   :linenos:

   import random

   colors = ['red', 'orange', 'yellow', 'green', 'blue', 'indigo', 'violet']

   # Select a random integer from 0 - 6:
   index = random.randint(0, len(colors)-1)

   # Save the random element from the list:
   color_choice = colors[index]

.. admonition:: Try It!

   Randomly change the color of the turtle before it draws each side of the
   polygon!

   Add the statement ``bob.color(random.choice(colors))`` to the code below.

   [Insert interactive repl here]

   .. sourcecode:: Python
      :linenos:

      import turtle
      import random

      bob = turtle.Turtle()
      bob.shape('turtle')
      bob.pensize(3)
      bob.speed(8)

      colors = ['red', 'orange', 'yellow', 'green', 'blue', 'indigo', 'violet']

      num_sides = 8

      for side in range(num_sides):
         bob.forward(75)
         bob.left(360.0/num_sides)

Random Turtle Walk
------------------

Let's have a little more turtle fun!

Up until now, we have always given a specific direction (``left`` or ``right``)
and angle whenever we turn a turtle. Lets throw in some random values to make
the path our turtle follows less predictable.

.. admonition:: Example

   Currently, the turtle takes 10 steps, and it always turns right by 90
   degrees. Make the following changes:

   #. Inside the loop, define a ``coin_toss`` variable and assign it the result
      of ``random.randint(0,1)``. As the name of the variable tells us, we can
      treat this like a coin toss, with ``0`` standing for heads and ``1``
      standing for tails.
      
      If you don't like working with 0 and 1, you can use
      ``random.choice('heads', 'tails')`` instead. However, numbers are easier
      to work with, and you are less likely to mistype 0 and 1.
   #. Place the turn command inside a conditional as follows:

      .. sourcecode:: Python
         :lineno-start: 13

         if coin_toss == 0:
            bob.right(90)
         else:
            bob.left(90)
      
      Thus, ``bob`` turns left or right depending on the random choice of 0 or
      1. Run the program again to see the result.
   #. Next, let's make bob rotate by a random number of degrees. Replace the
      argument ``90`` with ``random.randint(0, 180)``. Run the program several
      times to see the result.
   #. Finally, randomly assign the number of steps ``bob`` takes to a value
      between 5 and 25. Run the program several times to check your work.

   [Interactive repl here...]

   .. sourcecode:: Python
      :linenos:

      import turtle
      import random

      bob = turtle.Turtle()
      bob.shape('turtle')
      bob.speed(8)

      num_steps = 10

      for step in range(num_steps):
         bob.forward(50)
         coin_toss = random.randint(0,1)
         if coin_toss == 0:
            bob.right(90)
         else:
            bob.left(90)

Here are some bonus tasks for you to try as well:

#. Add a ``colors`` list and randomly assign a color to the turtle before each
   line is drawn.
#. Randomly select the length of each line drawn.
#. Randomly change the speed or pensize before or during the turtle's walk.
#. Move the walking code into a ``random_walk`` function that takes a turtle
   and the number of steps as parameters. Call ``random_walk`` to make ``bob``
   move.
#. Add a second turtle and have it take a stroll as well.

Check Your Understanding
------------------------

Lorem ipsum...
