What are Objects
================

A quick search of the web returns this fact:

   Python is an Object-Oriented Programming language (OOP).

In this book, we won't give a detailed explanation of what OOP means, but we
will take a closer look at the idea behind *objects*.

We have referred to objects in this book many times---turtle objects, string
objects, list objects, etc. However, we never explained what objects represent
in Python.

As a first step, let's review some vocabulary:

#. A *value* is a specific piece of data, like the integer ``3``, the string
   ``'hello'``, or the list ``[33, 45.2, 8]``.
#. A *function* is a defined, reusable block of code that performs a single,
   small task.

We assign values to variables so we can use that data later in our program. We
define and call functions to do something with that data or perform actions on
it. When we set up our programs this way, data storage and data manipulation
get carried out separately.

.. index:: ! object

**Objects** do both. They store data *and* perform actions on that data.
Objects give us a way to bring together all the parts of our code that relate
to a single idea.

.. index:: ! method, ! property

The data assigned to an object is called its **properties**. The actions an
object can perform are called its **methods**.

.. admonition:: Tip

   Think of an object like a smart phone.

   The *properties* of an object give us information about it. For a phone,
   this data includes things like brand, size, mass, color, amount of memory,
   etc.

   The *methods* of an object determine what it can *do*. For a phone, this
   would be the apps it contains. These allow the object to do things like take
   photos, send text messages, pay a bill, or even make a voice call.

Examples of Objects
-------------------

Lorem ipsum...

Why Use Objects?
----------------

Walk into your kitchen and you want to cook something. You could write a
``cook()`` function to call each time you want a meal. What would be the
required parameters? (Temp, time, device, setup). No need for a pre-heat
statement for a microwave. Instead of calling ``cook()`` and sending it a
device, we could create a device object and call a ``cook`` method specific to
that tool---``microwave.cook(), bbq.cook(), oven.cook(), stovetop.cook()``.

Do we ask our phone to look up the weather, or do we write instructions for
finding weather data and send a phone to that function? This shows the
difference between ``phone.weather()`` vs. ``show_weather(phone)``.

OOP
---

Most of the Python programs you have written so far contain statements that
gather data, do something with it, and then display the results. You included
functions to help streamline your code, and you called those functions as you
needed them. This style of programming focuses on the process of working with
the data---define or import a function to do a specific job, call that function
and send it some data, and then do something with the returned result.

An *object* wraps this process into a tidy package. A single object can store
data, perform actions on that data, and return the results of those actions. If
we bring together a collection of different objects, then we can build
programs in a much more flexible way. Each object controls its own data and
actions which breaks large programs into smaller and easier to control chunks.
