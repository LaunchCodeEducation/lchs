Adding Logic to Templates
=========================

Imagine we want to make a list of the top three pet names for a particular
year. The template code might look something like this:

.. sourcecode:: html
   :linenos:

   <h1>Top Pet Names of {{year}}</h1>
   <ol>
      <li>{{top_dog}} / {{top_cat}} / {{top_bird}}</li>
      <li>{{dog_2}} / {{cat_2}} / {{bird_2}}</li>
      <li>{{dog_3}} / {{cat_3}} / {{bird_3}}</li>
   </ol>

We would need to pass in 10 values to fill in the placeholders. While tedious,
it doesn't take that long to type the HTML for this list.

.. admonition:: Try It!

   Just for fun, time how long it takes you to type the template above.
   Copying and pasting the entire code block doesn't count!

Now imagine that we want to extend the list to the top 10, 20, 100, or 200 pet
names. Typing the HTML for *that* task doesn't sound fun at all! We are also
likely to make mistakes, so we need to plan on some debugging time as well.

Fortunately, there is a better way.

Loops in Templates
------------------

Short Python sample (for dog in dogs:). Multiple pets
(for index in range(len(...)):), use index values to put dog/cat/bird on one
line.

Use Python lists to store names. Use a loop with placeholders to automate the
``<li>`` elements.

For syntax and example...

Check JS Angular chapters for phrasing ideas...

Conditionals in Templates
-------------------------

Useful for showing/not showing content based on a condition.

If/else if/else syntax and examples...

Labels and Inputs
-----------------

Checkbox list.  Use {{}} for value attribute and label text.

Check Your Understanding
------------------------

Lorem ipsum...
