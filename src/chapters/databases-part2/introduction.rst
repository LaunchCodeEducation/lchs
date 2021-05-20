Introduction
============

Welcome to the end of LaunchCode's LCHS course! In this chapter, we will use
our Python, web development, and database skills to build a game application.
Each of the following pages includes a video tutorial, sample code, and a text
summary for one piece of the project.

.. index:: ! minimum viable product

The goal is to build a bare-bones Minesweeper game. Consider this a prototype
for a more refined program. By the end of the chapter, we will have a working
game, but it will contain a few gaps and rough edges. Repeated playing of the
game will identify improvements that *could* be made, but these won't prevent
the app from operating.

Once you have your prototype up and running, feel free to make changes and add
different features to make the project your own!

The video clip below demonstrates what the finished project will look like. It
also provides game instructions for those who might not be familiar with how to
play Minesweeper.

.. raw:: html

   <section class="vid_box">
      <iframe class="vid" src="https://www.youtube.com/embed/n2tXf33yAQk" frameborder="1" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
   </section>

Project Setup
-------------

#. Launch Visual Studio Code and open your ``local_practice`` directory.
#. Clone the Minesweeper starter code from GitHub. The project folder is
   called ``LCHS_Minesweeper_Game``.
#. Follow the usual process to install a new virtual environment. Name the
   new environment ``game-env``. (If you want to use a different name, 
   that's fine. Just remember to update the ``.gitignore`` file).
#. Activate the virtual environment and install Flask.

.. todo:: Add link to the Minesweeper GitHub repository.
