.. _deep-copy:

Copying Objects
===============

With both :ref:`lists <cloning-lists>` and :ref:`dictionaries <dictionary-copy-example>`,
we see that using an assignment statement like ``list_b = list_a`` does NOT
make a separate copy of the data. Instead, we just create a new label
(``list_b``) that points to the same memory location.

To make an independent clone of a list or dictionary, we use the ``.copy()``
method. Lists and dictionaries are both object types, and the class for each
one contains a set of code for making the copy.

What if an object does not have a ``.copy()`` method? We can still make an
independent clone, but the process is a little more involved. 

Shallow Copy
------------

Let's begin by reviewing how a simple assignment statement operates on an
object. 

.. admonition:: Example

   Line 11 creates a new object of type ``Student``, and line 12 creates a new
   *label* for the same object. ``student_1`` and ``student_2`` point to the
   same memory location.

   .. sourcecode:: Python
      :linenos:

      class Student:
         def __init__(self, name, id, scores):
            self.name = name
            self.id = id
            self.scores = scores

         def average(self):
            return round(sum(self.scores)/len(self.scores), 1)

      def main():
         student_1 = Student("Maria", 1234, [88, 95, 93])
         student_2 = student_1

         student_2.id = 7890

         print("student_1 =", vars(student_1))
         print("student_2 =", vars(student_2))

         student_3 = student_1.copy()

      main()

   **Console Output**

   ::

      student_1 = {'name': 'Maria', 'id': 7890, 'scores': [88, 95, 93]}
      student_2 = {'name': 'Maria', 'id': 7890, 'scores': [88, 95, 93]}

      File "main.py", line 19, in main
         student_3 = student_1.copy()
      AttributeError: 'Student' object has no attribute 'copy'

   The change we make to the ``id`` property on line 14 shows up when print the
   values using both ``student_1`` and ``student_2``. They are the same object,
   so changes made with one label show up when we use the other. 

   Note that line 19 throws an error. While list and dictionary objects both
   have defined ``.copy()`` methods, our ``Student`` object type does not.

Fortunately, we do not need to add a method to our ``Student`` class to copy
the objects. Python comes with a module, called ``copy``, that contains the
functions we need.

.. admonition:: Try It!

   In the editor below, note that we import one function from the ``copy``
   module. Not surprisingly, it's called ``copy``.

   To make an independent copy of an object, the general syntax is:

   .. sourcecode:: Python

      from copy import copy
      new_object = copy(old_object)

   #. Run the program as-is first to verify that ``student_1`` and
      ``student_2`` are the same object. Note the output from the three
      ``print`` statements.
   #. Replace line 14 with the statement ``student_2 = copy(student_1)``.
   #. Rerun the program and note the change in the output. With the updated
      code, ``student_1`` and ``student_2`` now represent different objects.

      Note that ``student_1 is student_2`` evaluates to ``False`` even when all
      of their property values match.

   .. raw:: html

      <iframe src="https://trinket.io/embed/python3/d235980037" width="100%" height="500" frameborder="1" marginwidth="0" marginheight="0" allowfullscreen></iframe>

While convenient, the ``copy()`` function is not the full story. It produces
what programmers call a *shallow copy* of an object. We will see what this
means in the next section.

Deep Copy
---------

.. index:: ! shallow copy, ! deep copy


