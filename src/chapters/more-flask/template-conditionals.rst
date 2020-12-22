Conditionals in Templates
=========================

In addition to loops, we can also include conditionals inside our Jinja2
templates. These evaluate :ref:`boolean expressions <boolean-expression>`, then
add or remove HTML elements to the webpage.

Conditionals come in handy when we need to choose whether or not to display
specific content.

``if/elif/else`` Syntax
-----------------------

The general syntax for a Jinja2 conditional is:

.. sourcecode:: HTML
   :linenos:

   {% if condition %}
      <!-- HTML code block -->
   {% endif %}

Just like in Python, ``condition`` is a boolean expression that evaluates to
``True`` or ``False``. If ``True``, then the following code block is added to
the webpage. If ``False``, the HTML is NOT generated, and the content stays off
the page.

We can include ``elif`` and ``else`` clauses to provide more flexibility for our
page design.

.. sourcecode:: HTML
   :linenos:

   {% if condition_1 %}
      <!-- HTML code block -->
   {% elif condition_2 %}
      <!-- Different HTML code block -->
   {% else %}
      <!-- Third HTML code block -->
   {% endif %}

Depending on the results of ``condition_1`` and ``condition_2``, one of the
three code blocks will be included on the page. The HTML in each part can be
any length and include any number of elements.

.. admonition:: Note

   A conditional determines if content is *added or removed* from a page. This
   is different from deciding if content should be *displayed or hidden*.

   *Hidden* content still occupies space on a page and requires some amount of
   memory. *Removed* content is absent from the page, requiring neither space
   nor memory. This is an important point to consider when dealing with things
   like images or videos.

Try It!
-------

Return to the pizza toppings form. Your next goal is to display the user's
selections after they click *Submit*. When the page first loads, this list and
its heading should not appear.

.. figure:: figures/toppings-list.png
   :alt: Checkbox form with selected options displayed to the side.
   :width: 60%

   You can show the choices below the form, if you wish.

#. Begin with the Python code. Open ``main.py`` and add some statements to
   retrieve the user's toppings and save them to a list.

   .. sourcecode:: Python
      :lineno-start: 6

      @app.route('/', methods=['GET', 'POST'])
      def checkbox_form():
         if request.method == 'POST':
            choices = request.form.getlist('toppings')
         else:
            choices = []

         pizza_toppings = ['pineapple', 'pepperoni', 'black olives', 'green peppers',
            'mushrooms', 'broccoli', 'extra cheese']
         return render_template('checkbox_form.html', pizza_toppings=pizza_toppings, choices=choices)

   a. Note the new syntax in line 9. Since the ``toppings`` input is a set
      of checkboxes, it is very likely that the user will select multiple
      options. The command ``request.form.getlist('toppings')`` collects the
      value from every checked box and adds it as an entry in the
      ``choices`` list.
   b. When the page first loads, it does so in response to a ``GET`` request.
      In this case, the ``else`` clause runs, and ``choices`` is assigned an
      empty list.
   c. Line 13 is outside of the ``if/else`` block, so it executes for both
      ``GET`` and ``POST`` requests.

#. Return to ``checkbox_form.html``. Right after the form, add a new section to
   display the user's topping choices.

   .. sourcecode:: html
      :lineno-start: 21

      <section>
         <h2>Your Choices</h2>
         <ul>
            {% for choice in choices %}
               <li>{{choice}}</li>
            {% endfor %}
         </ul>
      </section>

#. Save your work, then run the Flask application. Test the form to make sure
   the submission process works. Note that the ``Your Choices`` heading always
   shows up on the page.

Add the Conditional
^^^^^^^^^^^^^^^^^^^

The ``Your Choices`` heading and list should only appear after the user submits
the form. Time to add a conditional to the template!

#. Add just above h2.  If choices|length > 0
#. Lorem ipsum... 

Check Your Understanding
------------------------

Lorem ipsum...
