Styling Forms
=============

The forms we created in this chapter look pretty bland, since we stuck with
plain HTML. For example:

.. figure:: figures/bland-form.png
   :alt: A plain HTML form with the input fields too close together and a non-exciting appearance.

Visually, the form needs some work. First, the input fields don't line up
evenly. They don't have to, but aligning them makes our form look more
professional. Next, it would be nice to put some space between the boxes to
keep them from pushing right up against each other. Finally, the text is pretty
plain, and the button blends into the background.

Vanilla is a great ice cream flavor, but *vanilla HTML* makes a pretty weak web
form. We want visitors to our site to have a good experience, and presenting an
attractive page is a key part of this.

Here are a few tips to keep in mind when coding a form. None of these items are
*required*, but each one improves a user's experience with our work.

#. Include a short heading that identifies the purpose of the form.
#. Place only one input element on each line of the form. Vertically stacked
   fields are easier to navigate than side-by-side ones.
#. For text inputs, try to keep the width of the boxes the same. Also, have the
   fields line up with each other.
#. The part of the page that belongs to the form should be clear. Use shading
   or a border to separate the form from the other content on the page.
#. Break longer forms into multiple sections. Each section should deal with
   related information. For example, name and email would go in one section,
   while options for a lunch order would go in another.
#. The user shouldn't need to zoom in. Keep the font size large enough to
   easily read. (*Hint*: If your parent or teacher needs to squint and lean
   closer to the screen, bump up your font size).

Fortunately, we can meet these guidelines by applying some CSS style rules!

.. admonition:: Note

   One thing to keep in mind as we style our forms is that ``label``,
   ``input``, ``select``, ``textarea``, and ``button`` are all
   :ref:`inline elements <block-vs-inline-elements>`. Even if we put them on
   separate lines in our HTML code, they will appear in the same line of our
   webpage.

Add CSS
-------

Return to the ``main`` branch of your ``forms_chapter`` repository. Save and
commit any work, then use ``git checkout -b`` to make a new branch called
``form-style``.

Paste in this starter code for the ``form`` element:

.. sourcecode:: html
   :lineno-start: 13

   <form method="POST">
      <h2>A Few Of My Favorite Things</h2>
      <label>Favorite Color: <input type="text" name="color"/></label><br>
      <label>Lucky Number: <input type="number" name="luck-num"/></label><br>
      <label>Favorite Class: <input type="text" name="fav-class"/></label><br>
      <label>Favorite Pixar Movie: <input type="text" name="best-pix"/></label><br>
      <button>Submit</button>
   </form>

Save your work, then open the ``index.html`` file in your browser.

Margins
^^^^^^^

Let's start by putting some space between the inputs in our form. We will do
this by using the **margin** CSS property. *Margin* sets the amount of
whitespace that surrounds an element. The larger its value, the more spaced out
two neighboring elements will be.

#. Open the ``style.css`` file in Visual Studio Code.
#. Add this element selector in the file:

   .. sourcecode:: css
      :linenos:

      input, label {
         margin: 5px;
      }

#. Save, then refresh the page in your browser. Experiment with different
   ``margin`` values and note how the appearance of the form changes.
#. What happens to the form if your remove ``input`` or ``label`` from the CSS
   style rule?

Next, box width and alignment (right for label: input, left for label\ninput)...

Field shape, border, color...

Button shape, border, color...

Add sections to adjust internal alignment...

Add types to element selector to control style (e.g. input[type=text] {})...

References:

#. How to style forms with CSS: A beginner’s guide:
   https://blog.logrocket.com/how-to-style-forms-with-css-a-beginners-guide/
#. W3Schools: https://www.w3schools.com/css/css_form.asp
#. Dive deep with MDN docs:
   https://developer.mozilla.org/en-US/docs/Learn/Forms/Styling_web_forms

Use Bootstrap
-------------

Lorem ipsum...

Return to starter (vanilla) code...

Paste link into local repo...

Add classes to make a *form group*...

Try It!
-------

Lorem ipsum...
