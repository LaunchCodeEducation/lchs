The ``string`` Module
=====================

Besides checking if a variable holds a ``str`` data type or whether a character
is upper- or lowercase, we can also check to see if a character, slice or
string contains letters, digits, symbols, etc. 

The Python ``string`` module provides several constants that are useful for
these purposes. To use these constants, begin with an ``import`` statement at
the top of your code:

.. sourcecode:: Python
   :linenos:

   import string

Using ``string`` Constants
--------------------------

Let's say we want to check if one character from a string is a digit or a
lowercase letter. We could set up a conditional like so:

.. sourcecode:: Python
   :linenos:

   if char in '0123456789':
      # Code for the digit case...
   elif char in 'abcdefghijklmnopqrstuvwxyz':
      # Code for the lowercase letter case...
   else:
      # Alternate code here...

Note what we did:

#. Line 1 checks if the character is any of the digits 0 - 9,
#. If not, line 3 checks if the character is any of the lowercase letters from
   a - z.
#. We could easily expand the conditional to check for uppercase letters
   (``elif char in 'ABC...'``), punctuation, etc.

Although fairly straightforward, setting up the checks is tedious, since we need
to hard-code the strings for the numbers, letters, and symbols. (Go ahead and
type out the lowercase letters, then the uppercase letters, and then check for
any mistakes. How long did that take?)

Fortunately, Python has already defined the more common character combinations.
For example, ``string.digits`` is equivalent to ``'0123456789'``, and
``string.ascii_lowercase`` is the same as ``'abcdefghijklmnopqrstuvwxyz'``.

The table below summarizes several of the constants defined in the ``string``
module. For a complete list, refer to the
`Python documentation <https://docs.python.org/3/library/string.html>`__.

.. list-table:: Common String Methods
   :header-rows: 1

   * - Syntax
     - Description
   * - ``string.digits``
     - Returns the string ``'0123456789'``
   * - ``string.ascii_lowercase``
     - Returns the string ``'abcdefghijklmnopqrstuvwxyz'``
   * - ``string.ascii_uppercase``
     - Returns the string ``'ABCDEFGHIJKLMNOPQRSTUVWXYZ'``
   * - ``string.ascii_letters``
     - Returns a string containing all of the uppercase and lowercase letters.
   * - ``string.punctuation``
     - Returns the string ``'!"#$%&'()*+,-./:;<=>?@[\]^_`{|}~'``.

Try It!
^^^^^^^

Run the following code to see the values assigned to each ``string`` module
constant:

.. raw:: html

   <iframe height="650px" width="100%" src="https://repl.it/@launchcode/LCHS-String-Module-Intro?lite=true" scrolling="no" frameborder="yes" allowtransparency="true" allowfullscreen="true"></iframe>

Now try this:

#. Add ``elif`` blocks to the code to check if ``my_string`` is an uppercase
   letter, a digit, or some type of punctuation. Your code should print a
   different message depending on the value of ``my_string``.
#. Add an ``else`` statement to deal with characters that are not letters,
   digits, or punctuation.
#. Assign a longer string to ``my_string``. Add a loop to your code so that it
   checks each character in ``my_string`` and reports the results.
#. Note that *whitespace* characters are not included in any of these
   constants. Can you guess the name for the ``string`` module constant that
   contains ``' ', '\t'``, and ``'\n'``?

.. admonition:: Note

   Python contains a number of methods that return ``True`` or ``False`` based
   on the characteristics of an *entire* string instead of a single character.
   These can be used as alternatives to the examples above.

   For example, the ``isdigit()`` method returns ``True`` if ALL the characters
   in a string are digits. So ``'21'.isdigit()`` returns ``True`` while
   ``'21' in string.digits`` returns ``False``.

   Check out `W3Schools <https://www.w3schools.com/python/python_ref_string.asp>`__
   for more details about these methods.

Check Your Understanding
------------------------

.. admonition:: Question

   Which of the following expressions evaluate to ``False``? Select ALL that
   apply.

   .. raw:: html
      
      <ol type="a">
         <li><span id = "a" onclick="highlight('a', true)">'a' in string.ascii_uppercase</span></li>
         <li><span id = "b" onclick="highlight('b', false)">'Q' in string.ascii_letters</span></li>
         <li><span id = "c" onclick="highlight('c', true)">'334' in string.digits</span></li>
         <li><span id = "d" onclick="highlight('d', true)">' ' in string.punctuation</span></li>
         <li><span id = "e" onclick="highlight('e', false)">'$' in string.punctuation</span></li>
         <li><span id = "f" onclick="highlight('f', false)">'abc' in 'abcdefghijklmnopqrstuvwxyz'</span></li>
         <li><span id = "g" onclick="highlight('g', true)">'eo' in 'aeiou'</span></li>
      </ol>

.. Answers = a, c, d, g

.. raw:: html

   <script type="text/JavaScript">
      function highlight(id, answer) {
         text = document.getElementById(id).innerHTML
         if (answer) {
            document.getElementById(id).style.background = 'lightgreen';
            document.getElementById(id).innerHTML = text + ' - Correct!';
         } else {
            document.getElementById(id).innerHTML = text + ' - Nope! This is True.';
            document.getElementById(id).style.color = 'red';
         }
      }
   </script>
