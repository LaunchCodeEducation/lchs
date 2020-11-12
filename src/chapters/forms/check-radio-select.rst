Checkboxes, Radios, and Selects
===============================

The ``type`` examples on the previous page all used some form of text input.
However, the attribute also provides other options for collecting data from
the user.

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

.. list-table:: Three Non-Text Inputs
   :header-rows: 1

   * - Type
     - Description
     - Demo
   * - Checkboxes
     - Select any number of options. Boxes can be checked or unchecked by
       clicking in the box or on the label.
     - 
       .. raw:: html

          <form>
            <label><input type="checkbox" name="red"/> Red</label><br>
            <label><input type="checkbox" name="green"/> Green</label><br>
            <label><input type="checkbox" name="blue"/> Blue</label>
          </form>
   * - Radio Buttons
     - Only one choice per group is allowed. Once selected, a radio button
       CANNOT be unchecked by clicking on it again. (More on this below).
     -
       .. raw:: html

          <form>
            <label><input type="radio" name="color"/> Red</label><br>
            <label><input type="radio" name="color"/> Green</label><br>
            <label><input type="radio" name="color"/> Blue</label>
          </form>
   * - Select Menu
     - A drop-down menu that allows the selection of at least one item.
     -
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

A checkbox input gives the user one or more boxes to click. Checkbox inputs can
be used by themselves or in groups. For clarity and ease of use, each input
should be paired with its own ``label`` element.

The general syntax is:

.. sourcecode:: html

   <input type="checkbox" name="selection" />

When a form is submitted, a key/value pair is sent for *every* clicked
checkbox. The key is the same as the ``name`` attribute, and the default value
is ``on``.

.. todo:: Insert figure with 2 of 3 checkboxes clicked, plus parrot page.

If we want to send an option other than ``on``, we can include the ``value``
attribute inside the ``input`` tag.

.. sourcecode:: html

   <input type="checkbox" name="selection" value="value-when-checked" />

.. todo:: Insert figure with 2 of 3 checkboxes clicked, plus parrot page showing custom values.

Same vs. Different ``name``
^^^^^^^^^^^^^^^^^^^^^^^^^^^

In the examples above, each ``input`` element had a different ``name``
attribute. Each checkbox was considered ``on`` or ``off`` on its own. However,
let's see what happens if we give each checkbox in a group the same ``name``:

.. admonition:: Example

   [CODE BLOCK]

   [IMAGE of parrot page]

When we give a set of checkbox inputs the same ``name``, each one contributes
to the value assigned to the key. Instead of separate ``red``/``green``/``blue``
keys, we have a single ``color`` key that accepts the results from the entire
set of boxes.

Try It with the parrot server to see the format for the data returned.

Branch off of main to play with this.

Radio Buttons
-------------

Lorem ipsum...

Naming options - same vs. different.

Try It with the parrot server to see the format for the data returned.

Select
------

Lorem ipsum...

Syntax - select element with nested option elements...

disabled/selected/hidden/default attributes...

Choosing multiple options from the menu...

Try It!

Check Your Understanding
------------------------

Lorem ipsum...
