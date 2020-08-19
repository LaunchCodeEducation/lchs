What are Objects
================

A quick search of the web returns this fact:

   Python is an Object-Oriented Programming language (OOP).

In this book, we won't give a detailed explanation of what OOP means, but we
will take a closer look at the idea behind *objects*.

We have worked with objects many times already---turtle objects, string
objects, list objects, etc. However, we never explained what objects represent
in Python.

As a first step, let's review some vocabulary:

#. A *value* is a specific piece of data, like the integer ``3``, the string
   ``'hello'``, or the list ``[33, 45.2, 8]``.
#. A *function* is a defined, reusable block of code that performs a single,
   small task.

We assign values to variables so we can use that data later in our program. We
define and call functions to do something with data or perform actions on it.
When we set up our programs this way, data storage and data manipulation get
carried out separately.

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

Let's begin with a familiar example---strings.

.. sourcecode:: Python

   text = "I am an object."

All strings have a length property, and an individual character can be
classified as a letter, digit, punctuation, etc. Stings also include a property
that describes their case (upper or lower).

In addition to these properties, we can perform a defined set of actions on ANY
string value. These :ref:`string methods <string-methods-appendix>` take the
original string as data and return a new string. Examples include ``.upper()``
and ``.split()``.

Since strings contain both properties and methods (data and behaviors), they
are objects.

Another example of a Python object is a turtle.

.. sourcecode:: Python

   bob = turtle.Turtle()

Properties for the ``bob`` object include its color, speed, pen size, shape,
and location on the screen. Methods include actions like ``.forward()`` and
``.circle()``.

Anything related to the appearance or behavior of a turtle on the screen is
included with every turtle object. We do NOT need to define a ``left()``
function to rotate a turtle. The code for that behavior is part of the object
itself.
