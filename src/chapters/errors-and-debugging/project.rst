Project: Errors and Debugging
===============================

.. todo:: Add translation link here!

Avast, ye scurvy dogs! We be needn' ta fix yonder code!

The cap'n in charge of clearing our rocket for launch be out with a cold, and
ye be the next tech in line.

Yer job is to check the code and fix any bugs. Remember, the lives of the crew
rest upon yer shoulders. Happy second day on the job!

Yer directions:

#. Launch the rocket *only if* the fuel, crew and computer all check out OK.
#. If a check fails, print that information to the console and scrub the
   launch (then scrub the deck).
#. If all checks be successful, print a countdown to the console, then
   bellow "Liftoff!"

Fix Syntax Errors First
-----------------------

#. Run the following code as-is and squint yer eyes at the error message. Fix
   the mistake, and then re-run the code to check it.

   ::

      launch_ready = False
      fuel_level = 17000

      if fuel_level >= 20000
         print('Fuel level cleared.')
         launch_ready = True
      else:
         print('WARNING: Insufficient fuel!')
         launch_ready = False

   [INSERT REPL LINK HERE]

#. The next block of code hides two syntax errors. Run the code as-is to
   find the mistakes. *Tip*: Don't be too hasty, Matey! Only ONE error will
   be flagged at a time. Fix that ONE problem, and then re-run the code to
   check yer work. Avoid trying to fix multiple issues at once.

   ::

      launch_ready = False
      crew_status = True
      computer_status = 'green'

      if crew_status and computer_status = 'green':
         print('Crew & computer cleared.')
         launch_ready = True
      else:
         print('WARNING: Crew or computer not ready!')
         launch_ready = False

      if (launch_ready):
         print("10, 9, 8, 7, 6, 5, 4, 3, 2, 1...")
         print("Fed parrot...")
         print("Ignition...")
         print("Liftoff!')
      else:
         print("Launch scrubbed.")

   [INSERT REPL LINK HERE]

Fix Runtime Errors Next
-----------------------

#. Remember to examine the error message for clues about what is going wrong.
   Pay close attention to any line numbers mentioned in the message---these
   will help ye locate and repair the bug.

   ::

      launch_ready = False
      fuel_level = 17000

      if fuel_Level >= 20000:
         print('Fuel level cleared.')
         launch_ready = True
      else:
         print('WARNING: Insufficient fuel!')
         launch_ready = False

   [INSERT REPL LINK HERE]

#. *Arrr!*  Now find and fix the runtime error in a longer code sample.

   ::

      launch_ready = False
      fuel_level = 27000

      if fuel_level >= 20000:
         print('Fuel level cleared.')
         launch_ready = True
      else:
         print('WARNING: Insufficient fuel!')
         launch_ready = False
      }

      if launch_ready:
         print("10, 9, 8...")
         print("Fed parrot...")
         print("6, 5, 4...")
         print("Ignition...")
         printt("3, 2, 1...")
         print("Liftoff!")
      else:
         print("Launch scrubbed.")

   [INSERT REPL LINK HERE]

Solve Logic Errors Last
-----------------------

Logic errors do not generate warning messages or prevent the code from running,
but the program still does not work ye want. (Refer to the
:ref:`Fixing Logic Errors <fixing-logic-errors>` section if ye need to
review).

#. First, run this sample code as-is and examine the output.

   ::

      launch_ready = False
      fuel_level = 17000
      crew_status = True
      computer_status = 'green'

      if fuel_level >= 20000:
         print('Fuel level cleared.')
         launch_ready = True
      else:
         print('WARNING: Insufficient fuel!')
         launch_ready = False

      if crew_status and computer_status == 'green':
         print('Crew & computer cleared.')
         launch_ready = True
      else:
         print('WARNING: Crew or computer not ready!')
         launch_ready = False

      if launch_ready:
         print('10, 9, 8, 7, 6, 5, 4, 3, 2, 1...')
         print('Liftoff!')
      else:
         print('Launch scrubbed.')

   [INSERT REPL LINK HERE]

   Should the shuttle have launched? Did it?

#. Let's break the code down into smaller chunks. Consider the first ``if/else``
   block below. Add ``print(launch_ready)`` after this block, then run the
   program.

   ::

      launch_ready = False
      fuel_level = 17000

      if fuel_level >= 20000:
         print('Fuel level cleared.')
         launch_ready = True
      else:
         print('WARNING: Insufficient fuel!')
         launch_ready = False

   [INSERT REPL LINK HERE]

   Given the ``fuel_level`` value, should ``launch_ready`` be ``True`` or
   ``False`` after the check? Is the program behaving as expected?

#. Now consider the second ``if/else`` block. Add another
   ``print(launch_ready)`` after this block and run the program.

   ::

      launch_ready = False
      crew_status = True
      computer_status = 'green'

      if crew_status and computer_status == 'green':
         print('Crew & computer cleared.')
         launch_ready = True
      else:
         print('WARNING: Crew or computer not ready!')
         launch_ready = False

   [INSERT REPL LINK HERE]

   Given ``crew_status`` and ``computer_status``, should ``launch_ready`` be
   ``True`` or ``False`` after this check? Is the program behaving as expected?

#. Now consider both ``if/else`` blocks together (keeping the added ``print``
   lines). Run the code and examine the output.

   ::

      launch_ready = False
      fuel_level = 17000
      crew_status = True
      computer_status = 'green'

      if fuel_level >= 20000:
         print('Fuel level cleared.')
         launch_ready = True
      else:
         print('WARNING: Insufficient fuel!')
         launch_ready = False

      print(launch_ready)

      if crew_status and computer_status == 'green':
         print('Crew & computer cleared.')
         launch_ready = True
      else:
         print('WARNING: Crew or computer not ready!')
         launch_ready = False

      print(launch_ready)

   [INSERT REPL LINK HERE]

   Given the values for ``fuel_level``, ``crew_status`` and
   ``computer_status``, should ``launch_ready`` be ``True`` or ``False``? Is
   the program behaving as expected?

#. Ahoy, Houston! We spied a problem! The value of ``launch_ready`` assigned
   in the first ``if/else`` block got changed in the second ``if/else``
   block. Dangerous waters, Matey.
   
   Since the issue is with ``launch_ready``, ONE way to fix the logic error is
   to use a different variable to store the fuel check result. Update yer code
   to do this. Verify that yer change works by updating the first ``print``
   statement.

   [INSERT REPL LINK HERE]

#. Almost done, so wipe the sweat off yer brow! Add a final ``if/else`` block
   to print a countdown and "Liftoff!" if all the checks pass, or print "Launch
   scrubbed" if any check fails.

Blimey! That's some good work. Now go feed yer parrot.


