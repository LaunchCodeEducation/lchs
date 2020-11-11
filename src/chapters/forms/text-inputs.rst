Text Inputs
===========

Our first basic web form included two simple text inputs. The fields allow us
to enter whatever we want, and they display everything we type on the keyboard.
Inside the ``input`` tag, the ``type="text"`` attribute set up this behavior.

Besides ``text``, there are other options we can assign to the ``type``
attribute. Each one changes how the input field acts on the screen.

The table below summarizes several common ``type`` options. Try out each field
to see how it behaves.

.. role:: raw-html(raw)
   :format: html

.. list-table:: Different Text Input Types
   :header-rows: 1

   * - Type
     - Syntax
     - Description
     - Demo
   * - text
     - ``<input type="text" name="basic"/>``
     - A single line text field.
     - :raw-html:`<input type="text" name="basic"/>`
   * - number
     - ``<input type="number" name="num-choice"/>``
     - Browser validates the value is a valid number format.
     - :raw-html:`<input type="number" name="num-choice"/>`
   * - email
     - ``<input type="email" name="email-address"/>``
     - Browser validates the value is a valid email address format.
     - :raw-html:`<input type="email" name="email-address"/>`
   * - password
     - ``<input type="password" name="pass-code"/>``
     - A text field that hides the text typed by the user.
     - :raw-html:`<input type="password" name="pass-code"/>`
   * - date
     - ``<input type="date" name="flightDate"/>``
     - Browser validates the value is a valid date
       format. Some browsers provide a *date picker*.
     - :raw-html:`<input type="date" name="flightDate"/>`

.. admonition:: Note

   Form inputs will NOT look exactly the same in all browsers.
   However, the inputs *should* function the same way. Use `<https://caniuse.com>`_,
   if there is ever a question of browser support for a certain feature.

Example
-------

.. admonition:: Example

   .. sourcecode:: html
      :linenos:

      <form action="https://handlers.education.launchcode.org/request-parrot" method="post">
         <label>Code Name<input type="text" name="codeName"/></label>
         <label>Code Word<input type="password" name="codeWord"/></label>

         <!-- textarea must have open and closing tags -->
         <label>Mission Description<br/>
            <textarea name="description" rows="5" cols="75"></textarea>
         </label>

         <button>Send Report</button>
      </form>

   [IMAGE - Basic text fields screenshot]

   **Submitted Values**

   ::

      codeName=Captain+Danvers
      codeWord=avengers!
      description=Test+flight.+Plane+maintenance.+Superhero+stuff.

      Notice that the textarea value does NOT include new lines, even though it was typed that way.

      `Run it <https://repl.it/@launchcode/basic-inputs-example>`__

Check Your Understanding
------------------------

.. admonition:: Question

   Which input type should be used if the user is going to enter a large amount of text?


Specialized Text Inputs
-----------------------

Numbers, dates, times, email, password, etc.

Textarea...

textarea

``<textarea name="missionDescription"></textarea>``

A larger, multi-line text box. Must have open and closing tags.

:raw-html:`<textarea name="missionDescription"></textarea>`
