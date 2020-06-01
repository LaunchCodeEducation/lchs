Algorithms
==========

Have you ever alphabetized a stack of papers or a list of words? Did you sing
the alphabet song while you were performing the task? Did you sort the words
into groups based on the first letter? Did you "fan" the papers so you could
look at all of the names as you organized the stack? Did you get help from a
partner and split the task in half?

Regardless of how you completed the task, you probably followed a *pattern* to
make the process easier. If you had to repeat the task with a new set of words,
you could jump right and follow the same pattern.

.. index:: ! algorithm

The word **algorithm** is just a fancy name for a pattern or set of steps that
solve a specific problem.

Algorithms Are Easy to Find
---------------------------

Imagine a recipe for baking cookies. After the list of ingredients comes a
series of step-by-step instructions for making the treats. If you want to cook
something else, like a cake or a roast, you follow a different set of steps
using a different set of ingredients.

An *algorithm* is like a recipe. It is a careful series of steps that, when
followed, produce a specific result. Programmers create algorithms to solve
small tasks. By combining these small answers, programmers can solve much
larger problems.

For Example
^^^^^^^^^^^

Let's take a look at alphabetizing a list of words:

``apple, pear, zebra, box, rutabaga, fox, banana, socks, foot``

Here is one way to complete the task:

#. Arrange the words from a - z based only on the first letter:

   ``apple, box, banana, fox, foot, pear, rutabaga, socks, zebra``

#. If more than one word starts with 'a', rearrange those words based on the
   second letter. Repeat for the words that start with 'b', then 'c', etc.:

   ``apple, banana, box, fox, foot, pear, rutabaga, socks, zebra``

#. If multiple words start with 'a' and have the same second letter, rearrange
   those words based on the third letter. Repeat for the 'b' words, then the
   'c' words, etc.:

   ``apple, banana, box, foot, fox, pear, rutabaga, socks, zebra``

#. If other repeats exist, continue sorting the list by comparing the 4th, 5th,
   6th letters (etc.) until all the words are properly arranged.

This is not the ONLY way to solve the task, but it provides a series of steps
that can be used in many different situations to organize different lists of
words.

Alphabetizing is a process we can teach a computer to do, and the algorithm
will complete the process much more rapidly than a human. However, unlike the
alphabet song that many of us still sing in our heads, programmers must use a
different method to train the computer.

Check Your Understanding
-------------------------

.. admonition:: Question

   An algorithm is:

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> A solution to a problem that can be solved by a computer.</li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, true)"> A step by step list of instructions that if followed exactly will solve a problem.</li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> A single command run by a programming language.</li>
      </ol>
      <p id="Q1"></p>

.. Answer = b.

.. admonition:: Question

   Select ALL of the following that can be solved by using an algorithm:

   .. raw:: html
      
      <ol type="a">
         <li><span id = "a" onclick="highlight('a', true)">Answering a math problem.</span></li>
         <li><span id = "b" onclick="highlight('b', true)">Sorting numbers in decreasing order.</span></li>
         <li><span id = "c" onclick="highlight('c', true)">Making a peanut butter and jelly sandwich.</span></li>
         <li><span id = "d" onclick="highlight('d', true)">Assigning guests to tables at a wedding reception.</span></li>
         <li><span id = "e" onclick="highlight('e', true)">Creating a grocery list.</span></li>
         <li><span id = "f" onclick="highlight('f', true)">Suggesting new music for a playlist.</span></li>
         <li><span id = "g" onclick="highlight('g', true)">Making cars self-driving.</span></li>
      </ol>

.. Answer = all of the above.

.. raw:: html

   <script type="text/JavaScript">
      function highlight(id, answer) {
         text = document.getElementById(id).innerHTML
         if (answer) {
            document.getElementById(id).style.background = 'lightgreen';
            document.getElementById(id).innerHTML = text + ' - Correct!';
         } else {
            document.getElementById(id).innerHTML = text + ' - Nope!';
            document.getElementById(id).style.color = 'red';
         }
      }

      function evaluateMC(id, correct) {
         if (correct) {
            document.getElementById(id).innerHTML = 'Yep!';
            document.getElementById(id).style.color = 'blue';
         } else {
            document.getElementById(id).innerHTML = 'Nope!';
            document.getElementById(id).style.color = 'red';
         }
      }
   </script>
