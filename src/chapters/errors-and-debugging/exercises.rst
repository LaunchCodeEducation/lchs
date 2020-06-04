Exercises: Errors and Debugging
===============================

Programmers spend a lot of time reviewing other people's code to help them find
and fix bugs.

Assume you are part of a team, and you must get the following code samples
working. Do NOT just clear the editor and start from scratch! Part of working
well with others is to recognize their effort and what they did correctly.
Throwing away all of their code just because you would do it differently is NOT
a helpful strategy.

Find and Fix Syntax Errors
--------------------------

The following code sample contains X syntax errors.

#. Before making any changes, run the code as-is to generate the first error
   message.
#. Use the error message and any syntax highlighting to fix the first bug. Do
   NOT change anything in the code unless it involves fixing the first bug.
#. After changing the code, run the program again. If there is another bug in
   the program, you will see a different error message.
#. Repeat steps 2 and 3 until you fix all of the bugs and the program runs
   successfully.

.. todo:: Insert either an interactive repl or a link to a repl here (fixing syntax errors).

Find and Fix Runtime Errors
---------------------------

The following code sample contains Y runtime errors.

#. Before making any changes, run the code as-is to generate the first error
   message.
#. Follow the same process you used above to fix the runtime errors. Note that
   syntax highlighting does NOT show all possible runtime errors.

.. todo:: Insert either an interactive repl or a link to a repl here (fixing runtime errors).

Solve Logic Errors
------------------

#. The following code sample contains a logic error.  When given a student's
   score on an exam, the program *should* convert the points earned into a
   percentage. Find and fix the error so that the program *always* gives the
   correct result.

      Percentage = points earned / points possible * 100

   *Tip*: Use the following data to test the program and your fix.

   a. points_earned = 8, points_possible = 10, Final answer = 80.0%
   b. points_earned = 11, points_possible = 15, Final answer = 73.33333%
   c. points_earned = 23.4, points_possible = 25, Final answer = 93.6%

   .. todo:: Insert either an interactive repl or a link to a repl here (fixing a logic error).

#. The next code sample contains a logic error that involves the difference
   between ``>`` and ``>=`` (or ``<`` and ``<=``). When given a student's exam
   percentage, the program should convert it into a letter grade, assuming a
   standard scale:

   A: 100% - 90%
   B: 89 - 80
   C: 79 - 70
   D: 69 - 60
   F: < 60

   .. todo:: Insert either an interactive repl or a link to a repl here (fixing a logic error).

#. The last code sample contains a logic error that involves the *order* for
   ``if/elif/else`` statements. Given a value for ``fuel_level``, the
   program *should*:

   a. Print ``Fuel critical!`` if ``fuel_level`` falls below 1000.
   b. Print ``Fuel low`` if ``fuel_level`` falls between 1000 and 5000.
   c. Print ``Fuel below 1/2 tank.`` if ``fuel_level`` falls between 5001 and
      10000.
   d. Print ``Fuel below 3/4 tank.`` if ``fuel_level`` falls between 10001 and
      15000.
   e. Print ``Fuel tank full.`` if ``fuel_level`` is above 15000.
   f. Print ``Fuel error`` if ``fuel_level`` is below 0 or above 20000.

   .. todo:: Insert either an interactive repl or a link to a repl here (fixing a logic error).

