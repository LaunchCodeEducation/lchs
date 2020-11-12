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
attribute. Each checkbox was considered ``on`` or ``off`` on its own. Let's see
what happens when we give all the checkboxes in a group the same ``name``:

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
   #. Use ``git checkout -b`` to make a branch off of ``main``.
   #. In this new branch, modify your form to use a checkbox list with at least
      three options.
   #. Experiment with the ``name`` and ``value`` attributes to see how they
      behave.

Radio Buttons
-------------

Lorem ipsum...

Naming options - same vs. different.

Unselecting a Radio Button
^^^^^^^^^^^^^^^^^^^^^^^^^^

You can't... Note the two alternatives...

Try It with the parrot server to see the format for the data returned.

Select
------

Lorem ipsum...

Syntax - select element with nested option elements...

disabled/selected/hidden/default attributes...

Choosing multiple options from the menu...

Try It!

Other
-----

https://community.appway.com/screen/kb/article/checkboxes-radio-buttons-dropdowns-when-to-use-what-1482810890174

Check Your Understanding
------------------------

.. admonition:: Question

   What is the default value submitted for a ``<checkbox>`` when checked?

.. admonition:: Question

   Should a group of radio inputs have the same value for the ``name`` attribute?

.. admonition:: Question

   For a select input, what determines the value that is submitted during form submission?
