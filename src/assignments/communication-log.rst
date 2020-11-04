.. _communication-log:

Assignment #5: Communication Log
================================

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

#. Forking and cloning a repository from GitHub.
#. Adding partners to a shared GitHub Project.
#. Quickly trading code in ``push`` and ``pull`` cycles.
#. Merging two branches in GitHub.
#. Resolving merge conflicts (which are not as scary as they sound).

The Story
---------

You are going to carry out a conversation between a pilot and their base.
Between the two of you, choose who will be the **Pilot** and who will be the
**Base**. If you have three people in your group, add another pilot role.

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

#. **Base**: In a web browser, click the link to this `GitHub repository <https://github.com/LaunchCodeEducation/LCHS-Communication-Log-starter>`__.
   It contains the starter code needed for the assignment.
#. **Base**: In the upper right corner of the page, click the *Fork* button.
   This adds a copy of the repository to your own GitHub account.

   .. figure:: figures/com-log/fork-button.png
      :alt: The GitHub Fork button.

#. **Base**: Return to *your* GitHub home page and check for the
   ``communication-log`` repo. Click on its name to view it. The URL will look
   something like
   ``https://github.com/your-username/LCHS-Communication-Log-starter``. The
   ``your-username`` part of the address will show your GitHub name.

**Pilot**: Thanks for sitting by patiently!

Clone the Project from GitHub
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**Base** now has a copy of the repository in their GitHub account. The next
step is for each team member to *clone* that repo onto their personal device.

#. **Pilot and Base**: Open Visual Studio code. Use terminal commands to
   navigate into your ``local_practice`` directory. Use ``pwd`` to confirm your
   location.

   ::

      $ pwd
      /Users/username/Desktop/local_practice

#. **Pilot and Base**: In a browser, navigate to Base's copy of the repo (see
   step 3 above). Click on the green *Code* button. Select the ``HTTPS``
   option, then click the *Copy* button.

   .. figure:: figures/com-log/clone-button.png
      :alt: The GitHub Clone button.

      Clone a repository from GitHub.

#. **Pilot and Base**: In the terminal pane of VS Code, enter the
   ``git clone URL`` command. Replace ``URL`` with the address you copied from
   GitHub.

Add a Partner to the Repository
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

All team members should now have a local copy of the repository. However, only
**Base** can make changes to what is stored on GitHub. To fix this, one more
setup action is necessary.

#. **Base**: In your web browser, go to your ``communication-log`` repo. Click
   the *Settings* button then select the *Manage Access* option.

   .. figure:: figures/com-log/manage-access.png
      :alt: Click "Settings" and "Manage Access" to let other users modify the repo.
      :width: 70%

      Manage access to your repo.

#. **Base**: Click on the green *Invite a collaborator* button. Enter your
   partner's GitHub username and click *Add to repository*.

   .. figure:: figures/com-log/add-repo-partners.png
      :alt: Enter a GitHub username, then click the Add button.
      :width: 40%

      Choose who else can modify your GitHub repo.

#. **Pilot**: You should receive an email invitation to join this repository.
   View and accept the invitation.

.. admonition:: Note

   **Pilot**: If you don't see the email, check your Spam folder. If you still
   don't have the email, login to your GitHub account. Visit the URL for Base's
   copy of the repo. You should see an invite notification at the top of the
   page.

Whew! That was quite the setup experience. Now you're ready to dive into the
main part of the assignment.

Part B: First Message Exchange
------------------------------

In this part, you and your partner will take turns adding commits to the shared
code. Follow the steps carefully, and try not to get ahead of each other.

#. **Base**: In Visual Studio Code, open the ``index.html`` file from the
   repository. Replace ``Enter the first communication line here`` with a short
   greeting to your Pilot.
#. **Base**: Save and commit your change with the usual ``status/add/commit``
   process. Next, send your commit up to GitHub with the command:
   
   ::
   
      $ git push origin main

.. admonition:: Tip

   Remember that you can :ref:`open a local HTML file in your browser <view-local-html>`.
   If you do this with ``index.html``, then you can track your progress by
   refreshing the page after each change.

Pull Base's Line and Add Another Line
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

#. **Pilot**: In Visual Studio Code, open your local version of ``index.html``.
   Notice you don't have the new line of code that Base just added.
#. **Pilot**: In the terminal, enter this command to pull down the new code
   from GitHub:

   ::

      $ git pull origin main

#. **Pilot**: In VS Code, you should now see Base's greeting! Respond to this
   by adding a new HTML element and some text. Save, commit, and push your
   changes up to GitHub.

Pull Pilot's Line and Add Another
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

#. **Base**: Notice that *you* can't see what Pilot added yet. Fix this by
   entering ``git pull origin main`` in the terminal.
#. **Base**: Now add a third line to the log. Save, commit, and push your
   change up to GitHub.

Part C: Rinse and Repeat
------------------------

**Pilot and Base**: You can both play with this for a while! Repeat the cycle a
few more times to add to your story.

.. admonition:: Tip

   The story can go anywhere! Be creative, and try to make each other laugh. If
   possible, keep your new lines secret from your partner. That way, the
   ``pull`` result will be a surprise.

Part D: Create a New Branch
---------------------------

This back-and-forth workflow is nice, but it can get in the way. After all,
professional developers don't sit around waiting for their teammates to commit
and push a change before starting their own work. Fortunately, Git branches
allow partners to work on a project at the same time and at their own pace.

#. **Pilot**: While Base is working on the next part of the story, use the
   terminal to create a new branch called ``open-mic``.

   ::

      $ git checkout -b open-mic
      Switched to a new branch 'open-mic'
      $ git branch
        main
      * open-mic

#. **Pilot**: In VS Code, open ``style.css`` and add the following rule:

   .. sourcecode:: css
      :linenos:

      body {
         color: white;
         background-color: black;
      }

#. **Pilot**: Save and commit your changes. Next, push the new branch up to
   GitHub with the command:

   ::

      $ git push origin open-mic

#. **Base**: To pull down the new branch, enter the command:

   ::

      $ git pull origin open-mic

   .. admonition:: Note

      If you don't know the name of the new branch, then just enter ``git pull``.
      This will pull down *all* new branches and show you a list of the options.

#. **Pilot and Base**: If you haven't already done so, open ``index.html`` in
   a browser to see what it looks like.

Great! Now let's figure out how to merge two branches in GitHub.

Part E: Create a Pull Request In GitHub
---------------------------------------

You and your partner should both now find a second branch on the GitHub project
page. To see the branches, open the dropdown menu just above the list of files.

   .. figure:: figures/com-log/branches-dropdown.png
      :alt: GitHub dropdown menu showing available branches.
      :width: 60%

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

Make a Change in the New Branch
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

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

Part F: Merge the Pull Request
------------------------------

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

Merge Conflicts!
^^^^^^^^^^^^^^^^

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

Resolving Merge Conflicts
^^^^^^^^^^^^^^^^^^^^^^^^^

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

Pulling the Merged Code
^^^^^^^^^^^^^^^^^^^^^^^

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

Part G: More Merge Conflicts!
-----------------------------

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
---------

* `Git Branching - Basic Branching and Merging <https://Git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging>`__
* `Adding Another Person To Your Repository <https://help.Github.com/articles/inviting-collaborators-to-a-personal-repository/>`__
