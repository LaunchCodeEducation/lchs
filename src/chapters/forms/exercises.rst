Exercises: Web Forms
====================

Hello programmer, we need you to make a Rocket Simulation form. Please follow
the steps below. Happy coding!

Setup
-----

Instructions for creating two new files in ``forms_chapter repo``.

Branch off of ``main``?  Eventually merge?

.. todo:: Add code blocks for the ``rocket-sim.html`` and ``rocket.css`` files.

Part A: First Input
-------------------

#. Create a ``<form>`` with these attributes.

   a. Set ``method`` to ``"POST"``
   b. Set ``action`` to
      ``"https://handlers.education.launchcode.org/request-parrot"``.

#. Inside the ``form`` element, add a ``<label>`` and ``<input>`` for
   ``Test Name``:

   .. sourcecode:: html

      <label>Test Name: <input type="text" name="test-name"/></label>

#. Save your work, then open ``rocket-sim.html`` in your browser. What keeps
   you from submitting the form right now?
#. Add ``<button>Run Simulation</button>`` to your form.
#. Enter a value into the ``test-name`` input and submit the form. Was the
   key/value pair properly submitted to the server?

Save and commit your work before starting Part B.

Part B: More Inputs
-------------------

#. Next, add these five ``inputs`` to your form.

   a. Pay attention to the types and required values.
   b. Be sure to add a ``<label>`` for each input.

   .. list-table::
      :header-rows: 1

      * - Label
        - Input Type
        - Input Name
        - Required Values
      * - Test Date
        - ``date``
        - ``test-date``
        - Date format ``mm/dd/yyyy``
      * - Rocket Type
        - ``select``
        - ``rocket-type``
        - Options for ``Falcon``, ``Saturn``, ``Orion``, and ``Terrier``.
      * - Number of Engines
        - ``number``
        - ``engine-count``
        - A positive number less than 10.
      * - Wind Rating
        - ``radio``
        - ``wind-rating``
        - Options for ``No Wind``, ``Mild``, and ``Strong`` (see note below).
      * - Use Autopilot
        - ``checkbox``
        - ``autopilot``
        - ``on`` or ``off``

#. *Note*: Each ``wind-rating`` radio input needs to include a ``value``
   attribute. For ``No Wind``, set the value to ``0``. For ``Mild``, set the
   value to ``10``. For ``Strong``, set the value to ``20``.
#. Add placeholder text to the ``test-name`` and ``engine-count`` input fields.
#. Add an empty ``<option>`` element to the ``select`` input. Make it the
   default choice, include the ``value=""`` attribute, and set it to be
   ``disabled``.
#. Use the ``required`` attribute to add validation to the form. Prevent
   submission if any input *besides* ``autopilot`` is left blank.
#. Add a *Scrub Launch* button that resets the form.

.. admonition:: Example

   What the form will look like *before* submission.

      [IMAGE - Rocket sim example.]

   **Parrot Result**

      [IMAGE - Parrot results for rocket sim form.]

Part C: CSS Styling
-------------------

#. Add a heading, border, and background color to the form.
#. Lorem ipsum...
