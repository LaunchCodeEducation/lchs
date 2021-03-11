Saving Data
===========

Ideas...

Demo a Flask app that loses data after a refresh. Maybe a *movies to watch*
application?

   GIF of adding movies, then losing them when we click *Refresh*.

It looks like we're saving our movie watch list. However, once we refresh the
page, the list disappears! Even if we manage to build our code to save the list
as a global variable, once we end the program, that data still gets lost.

.. index:: ! persistent data

For many web applications, we want data to **persist**. This means saving the
information even if the user refreshes the page, closes the tab, or quits their
browser completely.

In this chapter, we will learn two ways to handle short-term data storage.
In the following chapters, we will use a something called a *database* to save
information over a longer period of time. 
