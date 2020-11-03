.. _communication-log:

Assignment #5: Communication Log
================================

Getting Ready: Code Together
----------------------------

Coding together allows you to work as a team so you can build bigger projects
faster. In this assignment, you will practice the common Git commands used when
two or more people work on the same project.

You and a partner will take turns modifying some shared code. The two of you
will work on your own devices, and you will push and pull your commits to a
GitHub repository.

In the Git :ref:`chapter exercises <git-exercises>` and
:ref:`project <git-project>`, you worked with both a local and a remote
repository. This assignment extends those ideas.

You will practice:

#. Quickly trading code in ``push`` + ``pull`` cycles.
#. Adding partners to a shared GitHub Project.
#. Cloning a repository from GitHub.
#. Merging two branches in GitHub.
#. Resolving merge conflicts (which are not as scary as they sound).

The Story
---------

You are going to carry out a conversation between a pilot and their control
base. Between the two of you, choose who will be the **Pilot** and who will be
the **Base**. If you have three people in your group, add another pilot role.

Even when it is not your turn to actively code something, watch what your
partner is doing. The steps in this activity mimic a real-world Git workflow
for a shared project.

.. admonition:: Warning

   You will be working with branches. It's very likely your team will
   accidentally add code to the wrong branch. When this happens, refer to the
   :ref:`git stash <git-stash>` notes to move your changes to the correct
   place.

Part A: Project Setup
---------------------

This part needs to happen on ONE person's computer. Whoever plays the role of
**Base** will git things rolling. However, the **Pilot** should definitely be
looking over Base's shoulder.

Instructions for forking a repo...

Part B: Share Your Repository On GitHub
---------------------------------------

Instructions for adding a collaborator to a repo...

**Base**: In your web browser, go to your ``communication-log`` repo. Click
the *Settings* button then click on *Collaborators*. Enter in Pilot's GitHub
username and click *Add Collaborator*.

   [IMAGE - Add a collaborator]

   CAPTION: Add a collaborator to your repo in GitHub

**Pilot**: You should receive an email invitation to join this repository.
View and accept the invitation.

.. admonition:: Note

   If you don't see an email (it may take a few minutes to arrive in your inbox),
   check your Spam folder. If you still don't have an email, visit the
   repository page for the repo that Base created (ask them for the link), and
   you'll see a notification at the top of the page.

   [IMAGE - The email invite to join a GitHub repository (height = 400 px)]

   CAPTION: Invited to collaborate email in GitHub

Part C: Clone the Project from GitHub
-------------------------------------

Both pilot and base do this...

Go to Base's GitHub profile and find the ``communication-log`` repo.
Click on the green *Clone or download* button. Use HTTPS (not SSH). Copy the
URL to your clipboard.

   [IMAGE - Clone button]

   CAPTION: Cloning a repository in GitHub  

In the terminal pane in VS Code, navigate to your Desktop folder and enter the
``git clone URL`` command. Replace ``URL`` with the address you copied from
GitHub.

Part D: First Message Exchange
------------------------------

Lorem ipsum...

Base first, then pilot pulls, then pilot responds, then base pulls...

Now you can respond to Base! Open the ``index.html`` file in your editor and
add your response to mission control. Be creative---the communication can go
anywhere! Just don't ask your partner what you should write. After you finish,
commit your change.

::

   $ git status
   On branch master
   Your branch is up-to-date with 'origin/master'.
   nothing to commit, working directory clean
   $ git add index.html
   $ git commit -m 'Added second line to log.'

Now we need to push up your changes so Base can use them as well.

Now let's go enter that command again to push up our code.

Anyone reading the HTML through GitHub's browser interface should now see the
new second line.

Part E: Pull Pilot's Line and Add Another Line
----------------------------------------------

**Base**: You might notice you don't have the second line of code in your
copy of the project on your computer. Let's fix that. Go to the terminal and
enter this command to pull down the updated code into your local git
repository.

::

   $ git pull origin master
   remote: Counting objects: 3, done.
   remote: Compressing objects: 100% (2/2), done.
   remote: Total 3 (delta 1), reused 3 (delta 1), pack-reused 0
   Unpacking objects: 100% (3/3), done.
   From github.com:username/communication-log
      e0de62d..e851b7e  master     -> origin/master
   Updating e0de62d..e851b7e
   Fast-forward
   index.html | 1 +
   1 file changed, 1 insertion(+)


Now, in your editor, add a third line to the communication. Then add, commit,
and push it up.

You can have your story go anywhere! Try to tie it in with what the pilot
wrote, without discussing with them any plans on where the story will go.

Step 7: Do It Again: Pull, Change, and Push!
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**Pilot**: You might notice now *you* don't have the third line on your
computer. Go to the terminal and enter this command to pull in the changes that
Base just made.

::

   $ git pull origin master
   remote: Counting objects: 3, done.
   remote: Compressing objects: 100% (2/2), done.
   remote: Total 3 (delta 1), reused 3 (delta 1), pack-reused 0
   Unpacking objects: 100% (3/3), done.
   From github.com:username/communication-log
      e851b7e..167684c  master     -> origin/master
   Updating e851b7e..167684c
   Fast-forward
   index.html | 1 +
   1 file changed, 1 insertion(+)

Now add a fourth line to the log. Again, be creative, but no planning!

Then add, commit, and push your change.

You can both play like this for a while! Feel free to repeat this cycle a few
times to add to the story.

Step 8: Create a Branch In Git
------------------------------

This workflow is a common one in team development situations. You might wonder,
however, if professional developers sit around waiting for their teammates to
commit and push a change before embarking on additional work on their own. That
would be a drag, and thankfully, there is a nice addition to this workflow that
will allow for simultaneous work to be carried out in a reasonable way.

**Pilot**: While Base is working on an addition to the story, let's make
another change simultaneously. In order to do that, we'll create a new branch.
Recall that a branch is a separate "copy" of the codebase that you can commit
to without affecting code in the ``master`` branch.

::

   $ git checkout -b open-mic
   Switched to a new branch 'open-mic'

This command creates a new branch named ``open-mic``, and switches your local
repository to use that branch.

Create a new file named ``style.css`` and add the following rules:

.. sourcecode:: css
   :linenos:

   body {
      color: white;
      background-color: black;
   }

Then link it in ``index.html``. It should look something like this:

.. sourcecode:: html
   :linenos:

   <html>
      <head>
         <link rel="stylesheet" type="text/css" href="style.css">
      </head>
      <body>
         <p>Radio check. Pilot, please confirm.</p>
         ... your content here
      </body>
   </html>

Now stage and commit these changes.

::

   $ git add .
   $ git commit -m 'Added style.css'
   $ git push origin open-mic

Note that the last command is a bit different than what we've used before
(`git push origin master`). The final piece of this command is the name of the
branch that we want to push to GitHub.

You and your partner should both now see a second branch present on the GitHub
project page. To view branches on GitHub, select *Branches* from the navigation
section just below the repository title.

   [IMAGE: Branches button in GitHub]

In your terminal, you can type this command to see a list of the available
branches:

::

   $ git branch
   * open-mic
   master

Note that creating and being able to see a branch in your local repository via
this command does NOT mean that the branch is on GitHub. You'll need to push
the branch for it to appear on GitHub.

.. note::

   The \* to the left of ``open-mic`` indicates that this is the active branch.


Great! Now let's show the other player your work in GitHub and ask them to
merge it in to the main branch.

Create a Pull Request In GitHub
-------------------------------

**Pilot**: If you haven't already, in your browser, go to the GitHub project
and click on *Branches* and make sure you see the new branch name, *open-mic*.

   [IMAGE: New PR button. (Height = 300 px)]

Click *New Pull Request* to begin the process of requesting that your changes
in the ``open-mic`` branch be incorporated into the ``master`` branch. Add some
text in the description box to let Base know what you did and why.

Note that the branch selected in the *base* dropdown is the one you want to
merge *into*, while the selected branch in the *compare* dropdown is the one
you want to merge *from*.

   [IMAGE: Create PR. (Height = 500 px)]

This is what an opened pull request looks like:

   [IMAGE: Open PR. (Height = 500 px)]

Step 10: Make a Change in the New Branch
----------------------------------------

**Base**: You will notice that you do not see the new ``style.css`` file
locally. Type this command to see what branches are on your local computer:

::

   $ git branch
   * master

If you want to work with the branch before merging it in, you can do so by
typing these commands:

::

   $ git fetch origin open-mic
   ...
   $ git branch
   open-mic
   * master

::

   $ git checkout open-mic
   Switched to branch 'open-mic'
   Your branch is up-to-date with 'origin/open-mic'.

Make a change, commit, and push this branch--you will see that the pull request
in GitHub is updated to reflect the changes you added. The context in the
description box is NOT updated, however, so be sure to add comments to the pull
request to explain what you did and why.

Now switch back to the ``master`` branch:

::

   $ git checkout master
   Switched to branch 'master'
   Your branch is up-to-date with 'origin/master'.

You will see your files no longer have the changes made in the ``open-mic``
branch. Let's go merge those changes in, so that the ```master``` branch adopts
all the changes in the ``open-mic`` branch.

Step 11: Merge the Pull Request
-------------------------------

**Base**: Go to the repo in GitHub. Click on *Pull Requests*.

   [IMAGE: PR-link.]

Explore this page to see all the information GitHub shows you about the pull
request.

   [IMAGE: open-pr.png. (Height = 500 px)]

When you're happy with the changes, merge them in. Click *Merge Pull Request*
then *Confirm Merge*.

   [IMAGE: Confirm merge. (Height = 500 px)]

Upon a successful merge, you should see a screen similar to the following:

   [IMAGE: pr-merged.png. (Height = 500 px)]

The changes from ``open-mic`` are now in the ``master`` branch, but only in
the remote repository on GitHub. You will need to pull the updates to your
``master`` for them to be present locally.

::

   $ git checkout master
   $ git pull origin master

Git is able to merge these files on its own.

Step 12: Merge Conflicts!
-------------------------

When collaborating on a project, things won't always go smoothly. It's common
for two people to make changes to the same line(s) of code, at roughly the same
time, which will prevent Git from being able to merge the changes together.

   [GIF: Merge conflict!]

This isn't such a big deal. In fact, it's very common. To see how we can handle
such a situation, we'll intentionally create a merge conflict and then resolve
it.

**Pilot**: Let's change something about the style file. Our HTML is looking
pretty plain, so let's pick a nice font and add some margins.

First, switch back to the ``master`` branch.

::

   $ git checkout master

Let's change our font. To do so, add this link to your ``index.html`` file,
right after the first stylesheet link:

.. sourcecode:: html

   <link href="https://fonts.googleapis.com/css?family=Satisfy" rel="stylesheet">


And spice up your ``style.css`` file to look like this:

.. sourcecode:: css
   :linenos:

   body {
      color: white;
      background-color: #333;
      font-size: 150%;
      font-family: 'Satisfy', cursive;
      margin: 5em 25%;
   }

The result:

   [IMAGE: fancy-text.png]

Stage and commit your changes and push them up to GitHub. If you don't remember
how to do this, follow the instructions above. Make sure you're back in the
``master`` branch! If you're still in ``open-mic``, then your changes will be
isolated, and you won't get the merge conflict you need to learn about.

Meanwhile...

**Base**: Let's change something about the style file that Pilot just
edited. Change it to look like this:

.. sourcecode:: css
   :linenos:

   body {
      color: white;
      background-color: black;
      font-family: 'Sacramento', cursive;
      font-size: 32px;
      margin-top: 5%;
      margin-left: 20%;
      margin-right: 20%;
   }

Don't forget to link the new font in your ``index.html`` file, after the other
link:

.. sourcecode:: html

  <link href="https://fonts.googleapis.com/css?family=Sacramento" rel="stylesheet">

Commit your changes to branch ``master``.

Step 13: Resolving Merge Conflicts
----------------------------------

**Base**: Try to push your changes up to GitHub. You should get an error
message. How exciting!

::

   $ git push origin master

   To git@github.com:username/communication-log.git
   ! [rejected]        master -> master (fetch first)
   error: failed to push some refs to 'git@github.com:username/communication-log.git'
   hint: Updates were rejected because the remote contains work that you do
   hint: not have locally. This is usually caused by another repository pushing
   hint: to the same ref. You may want to first integrate the remote changes
   hint: (e.g., 'git pull ...') before pushing again.
   hint: See the 'Note about fast-forwards' in 'git push --help' for details.


There's a lot of jargon in that message, including some terminology we haven't
encountered. However, the core of the message is indeed understandable to us:
"Updates were rejected because the remote contains work that you do not have
locally." In other words, somebody (Pilot, in this case), pushed changes to the
same branch, and you don't have those changes on your computer. Git will not
let you push to a branch in another repository unless you have incorporated all
of the work present in that branch.

Let's pull these outstanding changes into our branch and resolve the errors.

::

   $ git pull
   remote: Counting objects: 4, done.
   remote: Compressing objects: 100% (3/3), done.
   remote: Total 4 (delta 1), reused 4 (delta 1), pack-reused 0
   Unpacking objects: 100% (4/4), done.
   From github.com:username/communication-log
      7d7e42e..0c21659  master     -> origin/master
   Auto-merging style.css
   CONFLICT (content): Merge conflict in style.css
   Auto-merging index.html
   CONFLICT (content): Merge conflict in index.html
   Automatic merge failed; fix conflicts and then commit the result.


Since Pilot made changes to some of the same lines you did, Git was unable to
automatically merge the changes.

The specific locations where Git could not automatically merge files are
indicated by the lines that begin with ``CONFLICT``. You will have to edit
these files yourself to incorporate Pilot's changes. Let's start with
``style.css``.

   [IMAGE: Css conflicts.]

At the top and bottom, there is some code that could be merged without issue.

Between the ``<<<<<<< HEAD`` and ``=======`` symbols is the version of the code
that exists locally. These are *your* changes.

Between ``=======`` and ``>>>>>>> a48e8a75...``
are the changes that Pilot made (the hash ``a48e8a75...`` will be unique to
the commit, so you'll see something slightly different on your screen).

Let's unify our code. Change the CSS to look like this, making sure to remove
the Git markers so that only valid CSS remains in the file.

.. sourcecode:: css
   :linenos:

   body {
      color: white;
      background-color: black;
      font-family: 'Sacramento', cursive;
      font-size: 150%;
      margin: 5em 25%;
   }

.. tip:: Like many other editors, VS Code provides fancy buttons to allow you to resolve individual merge conflicts with a single click. There's nothing magic about these buttons; they do the same thing that you can do by directly editing the file.

   Feel free to use them, but beware that they will not always work. If you need to incorporate parts of a change from both branches, you will need to manually edit the file to resolved the conflict.

You will need to do the same thing for the ``index.html`` file. You only need
the link for the Sacramento font, not the Satisfy font. Then stage, commit, and
push your changes; you should not see an error message this time.

Step 14: Pulling the Merged Code
--------------------------------

**Pilot**: Meanwhile, Pilot is sitting at home, minding their own business. A
random ``git status`` seems reassuring:

::

   $ git status
   On branch master
   Your branch is up-to-date with 'origin/master'.
   nothing to commit, working directory clean


Your local Git thinks the status is quo. Little does it know that up at GitHub,
the status is not quo. We'd find this out by doing either a ``git fetch``, or
if we just want the latest version of this branch, ``git pull``:

::

   $ git pull
   remote: Counting objects: 13, done.
   remote: Compressing objects: 100% (8/8), done.
   remote: Total 13 (delta 4), reused 13 (delta 4), pack-reused 0
   Unpacking objects: 100% (13/13), done.
   From Github.com:username/communication-log
      0c21659..e0de62d  master     -> origin/master
   Updating 0c21659..e0de62d
   Fast-forward
   index.html | 3 ++-
   style.css  | 4 ++--
   2 files changed, 4 insertions(+), 3 deletions(-)

Great Scott! Looks like Base changed both ``index.html`` and ``style.css``.
Note that *Pilot* didn't have to deal with the hassle of resolving merge
conflicts. Since Base intervened, Git assumes that the team is okay with the
way they resolved it, and *fast forwards* our local repo to be in sync with the
remote one. Let's look at ``style.css`` to make sure:

.. sourcecode:: css
   :linenos:

   body {
      color: white;
      background-color: black;
      font-family: 'Sacramento', cursive;
      font-size: 150%;
      margin: 5em 25%;
   }

Step 15: More Merge Conflicts!
------------------------------

Let's turn the tables on the steps we just carried out, so Pilot can practice
resolving merge conflicts.

#. **Base and Pilot**: Confer to determine the particular lines in the code
   that you will both change. Make different changes in those places.
#. **Base**: Stage, commit, and push your changes.
#. **Pilot**: Try to pull in Base's changes, and notice that there are merge
   conflicts. Resolve these conflicts as we did above (ask Base for help, if
   you're uncertain about the process). Then stage, commit, and push your
   changes.
#. **Base**: Pull in the changes that Pilot pushed, including the resolved
   merge conflicts.

Merge conflicts are a part of the process of team development. Resolve them
carefully in order to avoid bugs in your code.

Resources
^^^^^^^^^^

* `Git Branching - Basic Branching and Merging <https://Git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging>`__
* `Adding Another Person To Your Repository <https://help.Github.com/articles/inviting-collaborators-to-a-personal-repository/>`__
