Why Use Objects?
================

Most of the Python programs you have written so far contain statements that
gather data, do something with it, and then display the results. You included
functions to help streamline your code, and you called those functions as you
needed them. This style of programming focuses on the process of working with
the data---define or import a function to do a specific job, call that function
and send it some data, and then do something with the returned result.

This style of programming works fine for small programs. However, as our
applications get bigger, reading, debugging and updating the code gets harder.

A Shift in Thinking
-------------------

An *object* wraps the processes of collecting and using data into one tidy
package. A single object can store data, perform actions on that data, and
return the results of those actions.

If we bring together a collection of different objects, each with its own
set of properties and methods, then we can build programs in a much more
flexible way. Each object controls its own data and actions. This lets us break
large programs into smaller and easier to control chunks.

.. todo:: Insert figure here! (OOP diagram vs. process oriented diagram).

Phones as Objects
-----------------

Take a look at the following code syntax:

.. sourcecode:: Python
   :linenos:

   show_weather(phone)

   phone.weather()

Line 1 shows a function call to ``show_weather``, and we pass ``phone`` as the
argument. We tell Python, *Give us a weather report, and use ``phone`` as the
data*.

Do we ask our phones to look up the weather, or do we write instructions for
finding weather data and send a phone to that function? This shows the
difference between ``phone.weather()`` vs. ``show_weather(phone)``.

Cooking
-------

Imagine you automate your kitchen so you can control it with code. What will
you do when you want to cook a meal?

You could define and code a ``cook()`` function to call each time you want to
make dinner. What data and parameters does this function need? Some options
include:

#. Cooking temperature,
#. Cooking time,
#. The device used,
#. Setup for that device.

Note that if you use a microwave, then there is no need to pre-heat the device
or specify a temperature. If you use the stove top, then the temperature will
just be a setting on the dial, like ``HI``, or ``4``. With this in mind, you
might try to code your ``cook()`` function to deal with different devices.

Instead of calling your ``cook()`` function and sending it data like:

.. sourcecode:: Python

   cook('oven', 'pizza')

you could create an *object* for a specific device and call a ``cook`` method
defined for that tool---``microwave.cook('pizza'), bbq.cook('peppers'),
crockpot.cook('pork roast')``, etc.

Each object has its own set of properties (temperature settings, setup, size,
etc.) that match only that cooking device. This allows us to code specific
cooking instructions for each object, 

Check Your Understanding
------------------------

Lorem ipsum...
