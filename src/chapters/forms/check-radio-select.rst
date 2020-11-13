Checkboxes, Radios, and Selects
===============================

The ``type`` examples on the previous page all involved some form of text
input. However, the attribute also provides other options for collecting data
from the user.

For example:

.. list-table:: Three Non-Text Inputs
   :header-rows: 1

   * - Checkboxes
     - Radio Buttons
     - Select Menu
   * - Select any number of options. Boxes can be checked or unchecked by
       clicking in the box or on the label.

       .. raw:: html

          <form>
            <label><input type="checkbox" name="red"/> Red</label><br>
            <label><input type="checkbox" name="green"/> Green</label><br>
            <label><input type="checkbox" name="blue"/> Blue</label>
          </form>
     - Only one choice per group is allowed. Once selected, a radio button
       CANNOT be unchecked by clicking on it again. (More on this below).
   
       .. raw:: html

          <form>
            <label><input type="radio" name="color"/> Red</label><br>
            <label><input type="radio" name="color"/> Green</label><br>
            <label><input type="radio" name="color"/> Blue</label>
          </form>
     - A drop-down menu that allows the selection of at least one item.

       .. raw:: html

          <form>
            <label>Choose a color: <br>
               <select>
                  <option disabled selected></option>
                  <option>Red</option>
                  <option>Green</option>
                  <option>Blue</option>
               </select>
            </label>
          </form>

Let's explore what we can do with each of these non-text inputs.

Checkboxes
----------

A checkbox input gives the user a single box to click. Checkboxes can be used
by themselves or in groups. For clarity and ease of use, each one should be
paired with its own ``label`` element.

The general syntax is:

.. sourcecode:: html

   <input type="checkbox" name="..." />

When a form is submitted, a key/value pair is sent for *every* clicked
checkbox. The key is the same as the ``name`` attribute, and the default value
is ``on``.

.. admonition:: Example

   Let's use the *Parrot Server* again to see the data received from a set of
   checkboxes. Note that each ``input`` element has its own ``name``.

   .. sourcecode:: html
      :linenos:

      <form action="https://handlers.education.launchcode.org/request-parrot" method="POST">
         <label><input type="checkbox" name="red"/> Red</label><br>
         <label><input type="checkbox" name="green"/> Green</label><br>
         <label><input type="checkbox" name="blue"/> Blue</label><br>
         <button>Send to Parrot</button>
      </form>

   .. figure:: figures/checkbox-1.png
      :alt: Selecting the 'Red' and 'Green' checkboxes sends values of "on" to the server.

      Checking a box assigns the value ``on`` to the ``name`` of the input element.

If we want a checkbox to stand for something other than ``on``, we can include
the ``value`` attribute inside the ``input`` tag.

.. sourcecode:: html

   <input type="checkbox" name="..." value="value-when-checked" />

.. admonition:: Example

   We've added ``value`` attributes to each ``input`` tag. Note that we also
   changed the ``name`` for each element.

   .. sourcecode:: html
      :linenos:

      <form action="https://handlers.education.launchcode.org/request-parrot" method="POST">
         <label><input type="checkbox" name="option_1" value="red"/> Red</label><br>
         <label><input type="checkbox" name="option_2" value="green"/> Green</label><br>
         <label><input type="checkbox" name="option_3" value="blue"/> Blue</label><br>
         <button>Send to Parrot</button>
      </form>
   
   .. figure:: figures/checkbox-2.png
      :alt: Adding "value" attributes changes the data assigned to each key.
      :width: 70%

      The ``value`` attribute lets us choose what gets assigned to the key.

Same vs. Different ``name``
^^^^^^^^^^^^^^^^^^^^^^^^^^^

In the examples above, each ``input`` element had a different ``name``
attribute. Let's see what happens when we give all the checkboxes in a group
the same ``name``:

.. admonition:: Example

   Each of the ``input`` elements in this form is named ``colors``. When
   clicked and submitted, the form will assign all of the selected ``values``
   to that key.

   .. sourcecode:: html
      :linenos:

      <form action="https://handlers.education.launchcode.org/request-parrot" method="POST">
         <label><input type="checkbox" name="colors" value="red"/> Red</label><br>
         <label><input type="checkbox" name="colors" value="green"/> Green</label><br>
         <label><input type="checkbox" name="colors" value="blue"/> Blue</label><br>
         <button>Send to Parrot</button>
      </form>
      
   .. figure:: figures/checkbox-3.png
      :alt: Checkboxes with the same name contribute to the same key/value pair.
      :width: 70%

      Multiple checkboxes contribute to a single key/value pair.
      
   Note that the value assigned to the ``colors`` key is a *list* containing
   the individual values of the clicked checkboxes.

When we give a set of checkbox inputs the same ``name``, each one contributes
to a single key. In this case, we have a single ``colors`` key that accepts
the results from the entire set of boxes.

.. admonition:: Try It!

   Return to your local ``index.html`` form.

   #. Save and commit your previous work to the repository.
   #. Use ``git checkout -b`` to make a branch off of ``main``. Call it
      ``checkboxes``.
   #. In this new branch, modify your form to use at least three checkboxes.
   #. Experiment with the ``name`` and ``value`` attributes to see how they
      behave.

Radio Buttons
-------------

Radio buttons appear as small circles instead of boxes. They allow a user to
pick one option from a group of choices. Only one radio input in a group can be
chosen at a time. The ``value`` attribute for that input will be submitted with
the form. Just like with checkboxes, every radio input should have its own
``<label>`` tags.

The general syntax is:

.. sourcecode:: html

   <input type="radio" name="..." value="value-when-selected"/>

To make a radio group work, all of the input elements must have the same
``name`` attribute.

.. admonition:: Example

   Let's convert the color checkboxes to a set of radio buttons.

   .. sourcecode:: html
      :linenos:

      <form action="https://handlers.education.launchcode.org/request-parrot" method="POST">
         <label><input type="radio" name="color" value="red"/> Red</label><br>
         <label><input type="radio" name="color" value="green"/> Green</label><br>
         <label><input type="radio" name="color" value="blue"/> Blue</label><br>
         <button>Send to Parrot</button>
      </form>
      
   .. figure:: figures/radio-parrot.png
      :alt: The 'Green' radio button is selected. This assigns the value 'green' to the 'color' key.
      :width: 70%

      The selected radio input sets the value for the ``color`` key.

Unselecting a Radio Button
^^^^^^^^^^^^^^^^^^^^^^^^^^

Take a look at the checkbox and radio options below. Try selecting and then
unselecting each one to see a key difference between the two input types.

.. raw:: html

   <label><input type="checkbox" name="newsletter"/> Sign me up for the newsletter!</label><br>
   <label><input type="radio" value="got-em"/> Yes, please send me more spam emails!</label>

Hmmm. Once we click the radio input, there is no quick way to undo that choice.
Depending on the browser settings, refreshing the page may or may not clear the
button. Try it. If that doesn't work, try a *hard refresh* by pressing
``control+shift+R`` on the keyboard (``command+shift+R`` on a Mac).

So how to we clear a radio input without refreshing the page? The quick answer
is, we can't. Once a user clicks a radio button in a group, one of the options
WILL be submitted with the form. The only way to avoid this is to not click any
of the choices in the first place, but that defeats the whole purpose of the
form.

The longer answer involves the user experience. It IS possible to clear a radio
group, but doing so is not straightforward. One option is to do a hard refresh,
but this clears the *entire* form. The user would have to start all over again,
which is annoying. Other options involve hacking into the form HTML inside the
browser. As good web developers, we shouldn't expect our users to need to do
this.

For a radio group, the best approach is to avoid the need to undo a choice. We
will revisit this idea later in the chapter. For now, here is one easy,
excellent tip:

.. admonition:: Tip

   In a radio group, ALWAYS include some kind of *No Choice* option. This gives
   the user an escape route if they don't like any of the other options.

   .. raw:: html

      <form action="https://handlers.education.launchcode.org/request-parrot" method="POST">
         <label><input type="radio" name="color" value="red"/> Red</label><br>
         <label><input type="radio" name="color" value="green"/> Green</label><br>
         <label><input type="radio" name="color" value="blue"/> Blue</label><br>
         <label><input type="radio" name="color" value=""/> None of the above</label><br>
      </form>

.. admonition:: Try It!

   Return to your local ``index.html`` form.

   #. Save and commit the work in the ``checkboxes`` branch.
   #. Return to ``main`` and checkout a new branch called ``radio``.
   #. In the new branch, modify your form to include at least three radio
      inputs.
   #. Submit your form to the parrot server to see how the data gets reported.
   #. What happens if you submit the form without clicking any of the radio
      buttons?
   #. What happens if you give each radio input a different ``name`` attribute?

Select
------

A *select* input creates a clickable menu that gives the user a drop-down list
of options. While it is possible to make the input accept more than one choice,
it's usually best to stick with allowing just one item.

The select input combines two HTML tags: ``<select>`` and ``<option>``. The
general syntax is:

.. sourcecode:: html

   <select name="...">
      <option value="...">First menu option.</option>
      <option value="...">Second menu option.</option>
      <!-- etc. -->  
   </select>

When the form gets submitted, the ``name`` attribute in the ``<select>`` tag
provides the key. The ``value`` attribute from the chosen ``<option>`` is
assigned to that key.

A select input works very much like a group of radio buttons.

.. admonition:: Example

   Let's use a drop-down menu to select our color choice.

   .. sourcecode:: html
      :linenos:

      <form action="https://handlers.education.launchcode.org/request-parrot" method="POST">
         <select name="color">
            <option value="red"> Red</option>
            <option value="green"> Green</option>
            <option value="blue"> Blue</option>
         </select>
         <button>Send to Parrot</button>
      </form>

   .. figure:: figures/select-parrot.png
      :alt: The 'Red' menu option is selected. This assigns the value 'red' to the 'color' key.
      :width: 70%

      The value of the selected ``option`` element is assigned to the ``color`` key.

Setting a Default ``<option>``
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

A ``select`` input always returns a value when a form is submitted, even if the
user never clicks on the menu. By default, ``select`` displays the first
``option`` element as the current choice.

Just like a radio button group, we should ALWAYS offer the user a *No Choice*
option. This can be an empty menu slot or some form of non-selectable title.

.. admonition:: Example

   Here are two examples of *no choice* options. Each one is placed first
   inside the ``select`` element, and the ``value`` attribute is assigned the
   empty string.

   .. sourcecode:: HTML
      :linenos:
   
      <!-- Example 1: Empty Top Slot -->
      <select name="color">
         <option value="" selected></option>
         <option value="red"> Red</option>
         <option value="green"> Green</option>
         <option value="blue"> Blue</option>
      </select>

      <!-- Example 2: Title -->
      <select name="color">
         <option value="" disabled selected>Choose a color:</option>
         <option value="red"> Red</option>
         <option value="green"> Green</option>
         <option value="blue"> Blue</option>
      </select>

   .. list-table::
      :header-rows: 1

      * - Example 1
        - Example 2
      * - .. raw:: html

              <select name="color"> Example #1
                 <option value="" selected></option>
                 <option value="red"> Red</option>
                 <option value="green"> Green</option>
                 <option value="blue"> Blue</option>
              </select>
        - .. raw:: html

              <select name="color">
                 <option value="" disabled selected>Choose a color:</option>
                 <option value="red"> Red</option>
                 <option value="green"> Green</option>
                 <option value="blue"> Blue</option>
              </select>

   The ``selected`` attribute sets the option as the default choice, which will
   be displayed when the user first loads the page. In Example 1, the blank
   menu slot can be chosen as an option.
   
   The ``disabled`` attribute in Example 2 (line 11) means that once the user
   picks a different option, the default title cannot be re-selected.

.. admonition:: Try It!

   Return to your local ``index.html`` form.

   #. Save and commit the work in the ``radio`` branch.
   #. Return to ``main`` and checkout a new branch called ``select``.
   #. In the new branch, modify your form to use a select input with at least
      three options.
   #. What happens if you submit the form without clicking the select menu?
   #. Experiment by placing the ``selected`` and ``disabled`` attributes inside
      different ``<option>`` tags.
   #. Try using the ``hidden`` attribute in place of ``disabled``. What does it
      do to the input?

When to Use What
----------------

Checkboxes, radio buttons, and the select drop-down menus all behave in a
similar way. However, they are NOT always interchangeable. When should we use
each input type?

Here are a few guidelines:

#. If the user needs to select multiple options, or be able to unselect items,
   go with checkboxes.
#. If the user must make a single choice from a long list, radio buttons work
   better than a drop-down menu.
#. Top-down lists are easier to read. Whenever possible, arrange a list of
   choices vertically instead of side-by-side.

`This article <https://community.appway.com/screen/kb/article/checkboxes-radio-buttons-dropdowns-when-to-use-what-1482810890174>`__
gives a nice summary of when to use each type of input and how to present clear
choices.

Check Your Understanding
------------------------

.. admonition:: Question

   What is the default value submitted for a ``<checkbox>`` when checked?

.. admonition:: Question

   Should a group of radio inputs have the same value for the ``name`` attribute?

.. admonition:: Question

   For a select input, what determines the value that is submitted during form submission?
