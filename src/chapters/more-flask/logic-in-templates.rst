Adding Logic to Templates
=========================

Imagine we want to display the top three pet names for a particular year. We
could easily create a list in Python to store these names, then pass that data
to a template.

.. admonition:: Example

   Yes, we can sends lists to our HTML template! Dictionaries and objects are
   allowed as well.

   .. sourcecode:: Python
      :linenos:

      @app.route('/popular_pet_names')
      def pet_names():
         year = 2020
         dogs = ['Bella', 'Max', 'Luna']
         cats = [ 'Luna', 'Bella', 'Oliver']
         birds = ['Kiwi', 'Blue', 'Sunny']
         return render_template('...', year = year, dogs = dogs, cats = cats, birds = birds)

The template code might look something like this:

.. sourcecode:: html
   :linenos:

   <h1>Top Pet Names of {{year}}</h1>
   <ol>
      <li>{{dog[0]}} / {{cat[0]}} / {{bird[0]}}</li>
      <li>{{dog[1]}} / {{cat[1]}} / {{bird[1]}}</li>
      <li>{{dog[2]}} / {{cat[2]}} / {{bird[2]}}</li>
   </ol>

While tedious, it doesn't take that long to type the HTML for a list with only
three rows.

Now imagine we want to extend the list to the top 10, 20, 100, or 200 pet
names. Typing the HTML for *that* task doesn't sound fun at all! Also, we would
probably make several mistakes, so we should plan for some debugging time.

Fortunately, there is a better way.

Loops in Templates
------------------

For now, let's just focus on the names for the dogs. With Python, we can easily
add or remove names to the ``dogs`` list. If we want to print these to the
console, we use a simple ``for`` loop.

.. sourcecode:: Python
   :linenos:

   for dog in dogs:
      print(dog)

Jinja2 allows us to do something similar inside a webpage. The general syntax
for a loop is:

::

   {% for item in collection_name %}
      {{item}}
   {% endfor %}

The symbols ``{% %}`` surround code statements, and they show where the loop
begins and ends. Each time the loop repeats, ``item`` takes the value of the
next element in ``collection_name``. The code does NOT appear on the webpage,
and the value for ``item`` gets inserted for the placeholder.

For the pet name template, the for loop would look like this. Note how line 3
looks just like the Python syntax, only without the ending colon, ``:``.

.. sourcecode:: html
   :linenos:

   <h1>Top Dog Names of {{year}}</h1>
   <ol>
      {% for dog in dogs %}
         <li>{{dog}}</li>
      {% endfor %}
   </ol>

Set up this way, the Jinja2 engine creates one ``<li></li>`` element for each
entry in ``dogs``. If we use our Python function to add or remove names, the
template responds by resizing the list in the browser.

.. admonition:: Note

   The purpose of loops in Jinja2 is *for display only*. They are NOT used to
   perform calculations or process data. That type of logic belongs in our
   Python code. 

Loops allow us to automatically create multiple HTML elements on a page. We
provide the tags, attributes, and any placeholders for a single entry. The
iteration copies that format and inserts different values each time the loop
repeats.

Using Index Values
^^^^^^^^^^^^^^^^^^

If we want to loop through a collection by index instead of by item, the syntax
for Python is:

.. sourcecode:: Python

   for index in range(len(collection)):

For Jinja2, the syntax replaces the ``len`` function with ``|length``.

.. sourcecode:: html

   {% for index in range(collection|length) %}

In both cases, ``index`` takes the values ``0, 1, 2...``

.. admonition:: Example

   We can use index values to complete our pet name list.

   .. sourcecode:: html
      :linenos:

      <h1>Top Pet Names of {{year}} (Dogs / Cats / Birds)</h1>
      <ol>
         {% for index in range(dogs|length) %}
            <li>{{dogs[index]}} / {{cats[index]}} / {{birds[index]}}</li>
         {% endfor %}
      </ol>

   Even if the lists for ``dogs``, ``cats``, and ``birds`` are not the same
   length, Jinja2 won't throw an *index out of range* error. Instead, the
   placeholders for the missing values show up as empty spots on the page.

   .. figure:: figures/animal-name-list.png
      :alt: Heading and a list showing the top 3 pet names for dogs, cats, and birds (2020).
      :width: 80%

      The 5th most popular bird name of 2020 was "Chicken".

These 6 lines of code only produce 4 lines of text on the webpage. However,
they have the potential to add many more as we expand the list of pet names.

Placement Matters
^^^^^^^^^^^^^^^^^

``{% for... %}`` and ``{% endfor %}`` repeat every element placed between them.
A small shift in the code can make a big difference in how the page renders.
For example, let's bring the ``<ol>`` tags inside the loop.

.. sourcecode:: html
   :linenos:

   <h1>Top Pet Names of {{year}} (Dogs / Cats / Birds)</h1>
   {% for index in range(dogs|length) %}
      <ol>
         <li>{{dogs[index]}} / {{cats[index]}} / {{birds[index]}}</li>
      </ol>
   {% endfor %}

Instead of one list with three different entries, this version of the code
produces three separate lists, each with only one element.

.. figure:: figures/repeat-ol.png
   :alt: Three lists, each with a single item labeled "1".
   :width: 60%

What do you think would happen if we moved the ``h1`` element inside the loop
as well?

Try It!
-------

Loops really come in handy whenever we need to build checkbox or radio inputs!

Checkbox list.  Use {{}} for value attribute and label text.

Check Your Understanding
------------------------

Lorem ipsum...
