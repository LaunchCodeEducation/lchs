.. _coded-messages:

Assignment #2: Coded Messages
=============================

With the amount of information flowing across the internet, keeping data secure
is an important concern. Keeping usernames, passwords, bank accounts, health
records, etc. safe requires constant work.

.. index:: ! encryption

**Encryption** refers to any process that converts information into a "secret
code" that hides its meaning from prying eyes. For example, messages can be
*encrypted* on one user's device, sent to another user, and then changed back
into plain text on the second device. Anyone intercepting the message
mid-stream will see unreadable characters.

For this assignment, you will create a program that changes plain text messages
into coded ones. Your program will also decode messages to produce readable
text.

.. todo::

   Insert link to starter code (assignment 2). Make sure it contains a
   ``main()`` function already defined.

Requirements
------------

By the END of this assignment, your program will:

#. Lorem ipsum...

Part 1: Simple Letter Shift (Caesar Cipher)
-------------------------------------------

You will begin with one of the basic code techniques, called the
`Caesar Cipher <https://en.wikipedia.org/wiki/Caesar_cipher>`__. This process
takes each letter in a message and replaces it with a different one. The new
letters are all *shifted* a certain number of spaces in the alphabet compared
to the originals.

.. todo:: Insert figure here (Caesar Cipher)

Open a new project in your code editor complete the following tasks.

The ``alphabet_position`` Function
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

#. Write a function called ``alphabet_position(letter)``, which receives a
   string containing a single letter. The function returns the *index* of that
   letter within the alphabet.
#. The function should be *case-insensitive*. Capital and lowercase letters
   should return the same result.

   .. list-table:: Sample Results
      :header-rows: 1

      * - ``letter``
        - Return Value
      * - a or A
        - 0
      * - d or D
        - 3
      * - z or Z
        - 24

#. *Don't forget to test your function!* In the ``main()`` function, call
   ``alphabet_position`` and send in different letters as arguments. Be sure to
   print the result returned to check your code.

.. admonition:: Tip

   #. You can assume the argument sent to the function will be a single letter.
      Do not worry about what do to with longer strings or non-letter
      characters.
   #. ``alphabet_position`` should NOT print anything. It needs to *return* a
      value instead.

The ``shift_character`` Function
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

#. Define the function ``shift_character(char, shift)`` with two parameters.
   ``char`` accepts a *character* (a string of length 1) and ``shift`` accepts
   an integer value.
#. If ``char`` is a letter, the function must return a different one. The new
   letter will be ``shift`` places to the right in the alphabet. The case of
   the letter should be preserved. For example, ``shift_character("A", 1)``
   returns ``"B"``, instead of ``"b"``.
#. If ``char`` is NOT a letter, then the function returns the same character.

   .. list-table:: Sample Results
      :header-rows: 1

      * - ``char``
        - ``shift``
        - Return Value
      * - a
        - 13
        - n
      * - D
        - 4
        - H
      * - z
        - 3
        - c
      * - J
        - 30
        - N
      * - !, 6, &, etc.
        - (any integer)
        - !, 6, &, etc. (no change for non-letter characters)

#. *Test your function!* In ``main()``, call ``shift_character`` and send in
   different characters and shift values. Be sure to print the letter returned
   to make sure your code works properly before moving on.

.. admonition:: Tip

   #. You should make use of your ``alphabet_position`` function! Thinking in
      terms of index values helps.
   #. Notice that the function "wraps around" when it reaches the end of the
      alphabet. If the shift amount moves the program past the letter ``'z'``
      (index value ``25``), it moves back to the start of the alphabet and
      continues counting with ``'a'`` (index value ``0``).
   #. The :ref:`modulus operator <modulus>` will be a BIG help here to keep the
      index values in the range 0 - 25.

The ``build_code_dict`` Function
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Lorem ipsum...

Part 2: Create Coded Message
----------------------------

Code ``encrypt_with_shift`` function...

Code ``decrypt_shift`` function...

Example Output
^^^^^^^^^^^^^^

Lorem ipsum...

Part 3: Keyword Shift
---------------------

Lorem ipsum...

Example Output
^^^^^^^^^^^^^^

Lorem ipsum...

Part 4: Add User Input
----------------------

Lorem ipsum...

Example Output
^^^^^^^^^^^^^^

Lorem ipsum...

Final Checks
------------

Before submitting your assignment, make sure your program:

#. Lorem ipsum...
