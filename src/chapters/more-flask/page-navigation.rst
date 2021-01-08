Page Navigation
===============

So far, we've used the address bar in the browser to access each webpage we've
built. Obviously, we need to do better than this. Users shouldn't have to type
in the address for every page they want to visit!

Adding links that connect to other pages in our website makes navigation much
easier. These links can take many forms, like a simple list of URLs, a set of
clickable icons, *Next Page* and *Previous Page* buttons, a dropdown menu, or a
nav bar. (You can find several of these options on this page!)

A List of Links
---------------

Let's start with a basic, unordered list. Each item will be a link that leads
to one of the pages in our website. For now, we will keep the design simple. We
can make it look nice after we get the navigation working.

Since we want the list to appear on every page, we will add it to the base
template.

#. Open ``base.html`` in Visual Studio Code.
#. Add a ``nav`` element below the ``endblock`` statement. Include a heading
   and an unordered list. Make one item for each of the pages you created
   earlier.

   .. sourcecode:: html
      :lineno-start: 15

      <nav>
         <h3>Page Navigation</h3>
         <ul>
            <li>Pizza Topping Form</li>
            <li>Second Page</li>
         </ul>
      </nav>

   Save your work, then launch ``main.py``. The list should appear on each page
   that extends ``base.html``.
#. Next, change the list items from text to active links.

   a. Wrap the text in link tags, ``<a></a>``.

      .. sourcecode:: html

         <li><a href="">Pizza Topping Form</a></li>
         <li><a href="">Second Page</a></li>
   
   b. Fill in the ``href`` values with the ``url_for()`` function:

      .. sourcecode:: html

         <li><a href="{{ url_for('checkbox_form') }}">Pizza Topping Form</a></li>
         <li><a href="{{ url_for('second_page') }}">Second Page</a></li>

   Note the arguments used inside ``url_for()``. The strings are the *names of
   the functions* from ``main.py``. They should NOT be the ``.html`` names you
   gave to the template files. The values you use inside ``url_for()`` will
   depend on the names you chose.
#. Save your work, then refresh the tab in the browser. Properly done, the
   navigation link should work something like this:

   .. figure:: figures/basic-nav.gif
      :alt: Clicking either of the two links in the list navigates to the chosen page.

      A list of links provides basic website navigation.

.. admonition:: Try It!

   When ``url_for()`` executes, it fills in the URL for the selected page. This
   will include the path used in ``@app.route()``. If you hover the pointer
   over a link, the URL will appear in the bottom corner of the browser window.

   .. figure:: figures/link-url.png
      :alt: Hovering over a link displays the target URL in the lower corner of the browser window.

Bring in Some Logic
-------------------

Update code to use a ``for`` loop to populate the list of links. A global
variable will be required in ``main.py``.

Change to a ``select`` Menu
---------------------------

Lorem ipsum...

This will keep the size of the menu consistent as our website grows!

Navigation Bar and Other Options
--------------------------------

Check Bootstrap (navbar option)... Down the rabbit hole!
https://getbootstrap.com/docs/5.0/components/navs-tabs/

GIF of Next and Back buttons...

This is beyond the scope of this course...

Links to useful resources?

https://medium.com/better-programming/building-your-first-website-with-flask-part-2-6324721be2ae

https://flask-menu.readthedocs.io/en/latest/

Check Your Understanding
------------------------

Lorem ipsum...
