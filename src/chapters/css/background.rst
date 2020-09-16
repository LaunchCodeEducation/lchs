What is CSS?
============

Background
----------

As discussed in the previous chapter, HTML lays out the structure of a webpage.
However, when programmers make pages only with HTML, the webpages look rather
bland.

.. todo:: Insert image of a simple, bland webpage here.

When building a website, the structure of each page is important, but so is the
appearance of the elements. By adding attributes inside the tags, programmers
can adjust how an element looks on the screen.

.. todo:: Insert image of a more attractive webpage here.

.. index:: ! css

The attributes themselves are considered *styling* information, not structure.
As such, we generally consider the styling of a webpage to be a separate task
from building the HTML layout.

While HTML creates the structure and content of the page, CSS adds the styling
to make it beautiful! Cascading Styling Sheets (**CSS**) is a style sheet
language that allows programmers to efficiently adjust add styling instructions
to HTML documents. With CSS, programmers can change background and font colors,
the size of different elements, and many more things.

CSS works by applying style rules to different elements. A style rule could be:
*Make this lettering purple* or *Make this font Helvetica*.

The *cascading* part of the CSS name refers to how the style rules get applied.
The rules "cascade" because they follow a specific order of importance.

.. admonition:: Note

   We will explore this order of importance later in the chapter. 

.. todo:: Insert image of HTML frame, CSS bells & whistles, and HTML+CSS.

Check Your Understanding
------------------------

.. admonition:: Question

   HTML is responsible for which parts of a webpage? Select ALL that apply.

   .. raw:: html

      <ol type="a">
         <li><span id = "a" onclick="highlight('a', true)">The structure</span></li>
         <li><span id = "b" onclick="highlight('b', true)">The content</span></li>
         <li><span id = "c" onclick="highlight('c', false)">The appearance</span></li>
         <li><span id = "d" onclick="highlight('d', false)">The web address</span></li>
      </ol>

.. Answers = a, b

.. admonition:: Question

   CSS is responsible for which part of a webpage?

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> The structure</li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> The content</li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, true)"> The appearance</li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> The web address</li>
      </ol>
      <p id="Q2"></p>

.. Answer = c

.. raw:: html

   <script type="text/JavaScript">
      function evaluateMC(id, correct) {
         if (correct) {
            document.getElementById(id).innerHTML = 'Yep!';
            document.getElementById(id).style.color = 'blue';
         } else {
            document.getElementById(id).innerHTML = 'Nope!';
            document.getElementById(id).style.color = 'red';
         }
      }

      function highlight(id, answer) {
         text = document.getElementById(id).innerHTML
         if (text.indexOf('Correct') !== -1 || text.indexOf('Nope') !== -1) {
            return
         }
         if (answer) {
            document.getElementById(id).style.background = 'lightgreen';
            document.getElementById(id).innerHTML = text + ' - Correct!';
         } else {
            document.getElementById(id).innerHTML = text + ' - Nope!';
            document.getElementById(id).style.color = 'red';
         }
      }
   </script>
