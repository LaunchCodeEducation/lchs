Conditionals in Templates
=========================

In addition to loops, we can also include conditionals inside our Jinja2
templates. These evaluate a boolean expression, then add or remove HTML
elements to the webpage.

Conditionals allow us to choose whether or not to display specific content.

``if/elif/else`` Syntax
-----------------------

The general syntax for a Jinja2 conditional is:

.. sourcecode:: HTML
   :linenos:

   {% if condition %}
      <!-- HTML code block -->
   {% endif %}

Just like in Python, ``condition`` is a :ref:`boolean expression <boolean-expression>`
that evaluates to either ``True`` or ``False``. If ``True``, then the HTML code
block is added to the webpage. If ``False``, then the HTML is NOT generated,
and the content stays off the page.

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

   An ``if`` statement determines if content is *added or removed* from a page.
   This is different from deciding if content should be *displayed or hidden*.

   *Hidden* content still occupies space on a page and requires some amount of
   memory. *Removed* content is absent from the page: requiring neither space
   nor memory. This is an important consideration when adding items like images
   or videos to your website.

Try It!
-------

Return to the pizza toppings form. Your next goal is to display the selected
options after the user clicks *Submit*. When the page first loads, this list
and its heading should not appear.

.. figure:: figures/toppings-list.png
   :alt: Checkbox form with selected options displayed to the side.
   :width: 60%

   You can show the choices below the form, if you wish.

#. Begin with the Python code. Return to ``main.py`` and add some statements
   to retrieve the user's toppings and save them to a list.

   [TODO: Enter code block here.]

   Note request.form.getlist('toppings')...

   Add MT choices list in else clause...
#. Test the form to make sure the submission process works... (Add placeholder
   for choices).

#. Return to ``checkbox_form.html``. Add a new section to display the user's
   topping choices.

   .. sourcecode:: html
      :lineno-start: 11

      <form action="/" method="POST">
         <h2>Select Your Pizza Toppings</h2>
         {% for topping in pizza_toppings %}
               <label><input type="checkbox" name="toppings" value="{{topping}}"/> {{topping}}</label><br>
         {% endfor %}
         <section class="centered">
               <button>Submit</button>
         </section>
      </form>

      <section>
         <h2>Your Choices</h2>
      </section>

#. Save, then reload the page. The ``Your Choices`` heading should appear on the
   page. However, we only want it there after the user submits some choices.

Check Your Understanding
------------------------

Lorem ipsum...
