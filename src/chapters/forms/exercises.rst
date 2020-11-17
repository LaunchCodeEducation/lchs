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
   ``Test Name``.

   .. sourcecode:: html

      <label>Test Name: <input type="text" name="test-name"/></label>

#. Save your work, then open ``rocket-sim.html`` in your browser. What keeps
   you from submitting the form right now?
#. Add ``<button>Run Simulation</button>`` to the ``<form>``.
#. Enter a value into the ``test-name`` input and submit the form. Was the
   key/value pair properly submitted to the server?

Part B: More Inputs
-------------------

#. Next add these five ``inputs`` to the ``<form>``.

   a. Pay attention to the types and possible options.
   b. Also add a ``<label>`` for each input.

.. list-table::
   :header-rows: 1

   * - Display Name
     - Input Type
     - Input Name
     - Possible Values
   * - Test Name
     - text
     - ``testName``
     - No limitations
   * - Test Date
     - date
     - ``testDate``
     - Date format mm/dd/yyyy
   * - Rocket Type
     - select
     - ``rocketType``
     - Brant, Lynx, Orion, Terrier
   * - Number of Rocket Boosters
     - number
     - ``boosterCount``
     - A positive number less than 10
   * - Wind Rating
     - radio
     - ``windRating``
     - No Wind: with value 0, Mild: with value 10, Strong: with value 20
   * - Use production grade servers
     - checkbox
     - ``productionServers``
     - on or off

.. admonition:: Example

   What the form will look like *before* submission.

      [IMAGE - Rocket sim example.]

   **Submitted Values**

   ::

      testName=Moon+Shot
      testDate=2020-07-16
      rocketType=Lynx
      boosterCount=3
      windRating=10
      productionServers=on

Bonus Mission
-------------

Use an event handler and the *submit* event to validate that all inputs have
values. Do NOT let the form be submitted if inputs are empty.
