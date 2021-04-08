.. _flask-game:

Assignment #6: Flask Game
=========================

In :ref:`Assignment #3 <console-game>`, you and a partner designed a simple
game app that ran in the console. This was a great step in creating your own
complete program from start to finish.

Now that you have some Flask experience, your team can move the game out of the
console and into a browser!

.. admonition:: Example

   On the left is the same console Rock-Paper-Scissors example from Assignment
   3. The right hand side shows what it could look like in a browser.

   Insert screenshots, GIFS, or Trinket editor showing the differences between
   a console rock-paper-scissors game and a web-based one...

If your teacher didn't ask you to complete the :ref:`Console Game <console-game>`
assignment, you should review that page to get some ideas about how the game
needed to operate.

If you DID create a console game but want to create a different one for the
browser, that's fine! You are free to recycle an old idea or think up something
completely new. For example, maybe your teacher had you code a
choose-your-own-adventure program after chapter 5. Imagine what that would look
like on the web, with each choice updating the page or redirecting to a
different one.

.. _assignment6-requirements:

Requirements
------------

To be considered complete, your application must include each of the following:

#. A web form to collect user input.
#. At least two HTML templates, one of which can be a ``base.html`` file. These
   should include placeholders to display data that can change when the page
   reloads.
#. CSS styling, either from a local ``style.css`` file or from
   :ref:`Bootstrap <bootstrap-classes>`.
#. At least one Jinja2 loop or conditional within the template(s).
#. Both client-side and server-side validation.
#. Python code that:

   a. Renders the required templates,
   b. Collects user input from the web form,
   c. Creates, accesses, modifies, or deletes data from a Flask ``session``,
   d. Generates feedback messages for the user,
   e. Runs the game!

Part 1: Choose an Idea
----------------------

Before you dive in, you and your partner must decide on the path you want to
follow.

**If you want to recycle code from an earlier game**:

#. Discuss what you want the game to look like in the browser. Make sketches
   for each of the planned webpages.
#. Decide if you will use a ``base.html`` template. If so, consider what HTML
   elements you want to put in that file.
#. Examine your old Python code and determine what needs to be replaced. For
   example, console games rely on ``print`` statements to display text. Flask
   applications send data to an HTML file instead.
#. Identify which of your old functions can be used as-is. Importing them as a
   module will save you some time and effort.
#. Decide which functions need to be refactored or replaced completely. These
   might be mostly correct, but they need modifications to render a template
   and/or collect data.

**If you want to start with a new game**:

#. Brainstorm! Describe to each other what you want the game to do.
#. Write down the features you want your game to have.
#. Start simple! From your features list, select only the most important ideas
   for your game. You have a limited amount of time, and you can always add
   more features later.
#. Identify what information needs to be displayed in the browser (intro,
   forms, results, etc.).
#. Make sketches for what your game will look like in the browser. How many
   templates will you need? Will you use a ``base.html`` template?
#. Create a general outline for the functions your application is going to
   need.

.. admonition:: Note

   Regardless of whether you recycle old code or not, your Flask application
   is going to need multiple functions! Even if your app only renders one
   webpage, you should NOT cram all of the game logic into the same place.
   Remember, functions should be small and accomplish only one task.

   Not every function in a Flask app has to render a template. It's perfectly
   fine for a function to serve a supporting role instead.

Part 2: Create a GitHub Repository
----------------------------------

Lorem ipsum...

You will store your project code in GitHub.

Make branches! To save time, one partner can focus on the page design
(HTML/CSS), and the other can focus on the game logic.

Part 3: Code the Flask Application
----------------------------------

Lorem ipsum...

Part 4: Test Your Game
----------------------

Your team has run the application lots of times to check different pieces. Now
it's time to challenge your game! The goal here is to find bugs by deliberately
trying to break the program.

.. index:: edge cases, ! beta tester

#. Start by checking the web form. Be brutal! Any errors you miss will
   eventually be found by visitors to your site.
   
   a. What happens when you submit an invalid entry?
   b. What happens when you refresh the page or reload it from the address bar?
   c. What if you try to submit duplicate entries?
   d. What if you submit HTML code?
   e. What if you use the browser tools to remove the ``required`` attribute
      from the ``input`` tag and submit an empty response?

#. Test **edge cases**, which are entries that fall at the ends of an accepted
   range (like ``1`` and ``10`` in the range ``1 - 10``).
#. If users must make a series of choices in the game, test every possible
   order and combination of those choices.
#. Play the game like it's the first time you've seen it. Don't just run
   through the actions that you *know* work.
#. Proofread the game instructions. Are they clear? How might users
   misinterpret them?
#. Find one or more **beta testers**. These are people who had no other role
   in creating your game.

Scoring
-------

Before you submit your application, be sure that it:

#. Works.
#. Provides a good user interface and user experience.
#. Meets each of the :ref:`project requirements <assignment6-requirements>`.
#. Survives invalid input. For example, if your program asks the user to enter
   a number, it should not crash when they enter a letter.
#. Includes enough comments in the code to describe what each part does.
#. Is fun to play!

Your teacher will provide you with a detailed **rubric** for this assignment.
This describes how each part of the project will be graded, as well as how
many points each part can earn.

Submitting Your Work
--------------------

Your teacher will provide instructions for sharing the URL for your project
and/or demonstrating your application to the class.
