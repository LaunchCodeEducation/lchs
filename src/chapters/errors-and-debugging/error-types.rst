Types of Errors
===============

Each type of error---syntax, runtime, and logic---shows itself in a different
way. Also, some strategies may be more useful for certain types of errors
compared to others.

Stages for Running a Python Program
-----------------------------------

In order to understand programming errors it is useful to understand the two
stages of code execution.

Parsing
^^^^^^^

.. index:: ! code parsing

Before code can be run, it must be validated and prepared for execution. This is
known as the **parsing stage**. Think of it like the pre-flight checklist
pilots use before taking off. If errors are found, the plane stays on the
ground.

When we click *Run* to start our code, parsing begins. A lot of detailed tasks
happen behind the scenes during this process, but we just need to know that
parsing checks the syntax and structure of the code. If any mistakes are found,
the program does not launch.

Execution
^^^^^^^^^

If parsing finishes without finding any errors, check, the program is ready to
run. The **execution stage** is when the statements written into our
code---printing to the console, prompting the user for input, making
calculations, etc.---are actually carried out. Think of this stage as
the plane taking flight.

Syntax Errors
-------------

.. index:: syntax

Python can only execute a program if the program is *syntactically correct*.
**Syntax** refers to the structure of a language (spoken, programming, or
otherwise) and the rules about that structure. For example, in English,
a sentence must begin with a capital letter and end with appropriate
punctuation.

.. index::
   single: error; syntax

A **syntax error** occurs when we break one of the rules for a given language.

.. admonition:: Examples

   this sentence contains a syntax error. 

   So does this one

For most readers, a few syntax errors are not a big problem. Our brains are
flexible enough to figure out a sentence even if it contains one or more syntax
errors.

Programming languages are not so forgiving. If there is a single syntax error
anywhere in our program, Python will display an error message and immediately
quit. Since syntax is checked during the parsing stage, these errors are
found first.

As you practiced your coding skills during the past several chapters, you
probably spent some time tracking down syntax errors. As you gain experience,
you will make fewer of these mistakes, but they will never disappear completely.
However, you will get good at quickly finding syntax errors.

.. admonition:: Try It!

   Find the syntax errors in the program.

   .. raw:: html

      <iframe height="400px" width="100%" src="https://repl.it/@launchcode/LCHS-Syntax-Error-Example?lite=true" scrolling="no" frameborder="yes" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

   #. What syntax errors did you find?
   #. What was the error message provided by Python in each case?
   #. Pay attention to any line numbers given in the error message.

Runtime Errors
--------------

.. index::
   single: error; runtime

.. index:: ! exception, ! runtime error

Once the syntax for your code is correct, the program launches. However,
mistakes can still occur and cause the program to crash. These mistakes are
called **runtime errors** because they do not appear until we run the program.
The errors are also called **exceptions** because they usually indicate that
something exceptional (and bad) has happened.

Runtime errors occur during the execution phase of a program, so we only
see them *after* all syntax mistakes are fixed.

Common runtime errors include:

#. Misspelling a variable name.
#. Using an index value that is too large for a given string or list.
#. Incorrect math operations (like dividing by zero).
#. Comparing different data types.

.. admonition:: Examples

   Run the following code to produce an error message. Read the message, fix
   the error, then re-run the program.

   Continue this process until no more error messages appear. Fix only one
   error at a time.

   .. raw:: html

      <iframe height="600px" width="100%" src="https://repl.it/@launchcode/LCHS-Runtime-Error-Examples?lite=true" scrolling="no" frameborder="no" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

   Make a note of name (e.g. ``IndexError``) given to each of the runtime
   errors you find in the code. Also notice that the error message gives you
   the line number where the mistake occurred.

The *syntax* in the code is correct, but when the program runs, an error occurs
that Python cannot solve. For example, on line 8, we try to print the value
``first_name``, but the variable does not exist! (In line 4, we defined
``first_Name`` instead).

Logic Errors
------------

.. index::
   single: error; logic

The third type of error is the **logic error**. If there is a logic error in your program, it will run successfully and not generate any error messages. However, the program will not work as intended.

The characteristic of logic errors is that the program you wrote is not the program you wanted. For example, say you want a program to calculate your daily earnings based on your weekly salary. You might try the following:

.. admonition:: Example

   .. sourcecode:: js
      :linenos:

      let weeklyPay = 600;

      let dailyEarnings = weeklyPay / 7;
      console.log(dailyEarnings);

   **Console Output**

   ::

      85.71428571428571

The result surprises you because you thought you were making at least $100 per day (you work Monday through Friday). According to this program, though, you are making about $85 per day. The error is a logic one because you divided your weekly pay by 7. It would have been more accurate to divide your weekly pay by 5, since that is how many days a week you come to work. 

Identifying logic errors can be tricky because unlike syntax and runtime problems, there are no error messages to help us identify the issue. We must examine the output of the program and work backward to figure out what it is doing wrong.

Check Your Understanding
------------------------

.. admonition:: Question

   Label each of the following as either a syntax, runtime, or logic error.

   #. Trying to use a variable that has not been defined.
   #. Leaving off a close parenthesis, ``)``, when calling ``console.log``.
   #. Forgetting to divide by 100 when printing a percentage amount.
