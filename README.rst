MadLibs: A Flask Demo
=====================

In this demo, we'll create a simple Flask application that plays MadLibs. The
flask docs (http://flask.pocoo.org/docs/0.10/) are about to become your bestest friend.

Clone This Repo
---------------

We're giving you a skeleton webapp to start with. Go in to your src directory and::

     git clone https://github.com/hackbrightacademy/flask-madlibs.git

Setup
-----

1. In your project directory, create a "virtual environment" so we don't have
   to install Flask (or other special libraries) system-wide::

     virtualenv env

2. And start using your virtual environment::

     source env/bin/activate

3. Install Flask::

     pip install Flask

   (this will run for a moment and will download and install several Python libraries)


Running the Application
-----------------------

1. If you haven't done so in this terminal window, start using your virtual environment::

     source env/bin/activate

   (Notice what changes about your command line prompt when you are in a virtual Python
   environment)

2. Run the application::

     python madlibs.py


Testing the Application
-----------------------

1. Visit http://localhost:5000/

   This URL is "routed" to the function ``start_here()`` and returns a simple string:
   "Hi! This is the home page."

2. Visit http://localhost:5000/hello

   This is routed to the function ``say_hello()`` and shows a simple form which asks
   your name. It is rendering a template called ``templates/hello.html``.

3. Submit the form. This will send you to http://localhost:5000/greet?person={your name here}

   This URL, "/greet", is routed to ``greet_person()``. This page is getting the
   name entered in the previous form via ``request.args.get(person)``, choosing a
   random compliment, and passing both the person variable and the compliment
   to the function that renders the template at ``templates/compliment.html``.
   Reload this page a few times.
   Change the text after the ``person=`` in the URL and hit return. Notice how the
   page changes.

Your Task
---------

Now that we've got a solid foundation for our first webapp, let's have some fun.

1. Modify the template ``compliment.html`` to ask the person if they'd like to play
   a game (hint: try radio buttons!). Have this form submit to the URL path ``/game``.

2. Make a function called ``show_game_form`` and route this to the URL path ``/game``, so
   that when users fill out your "play a game?" form, it uses this function.

3. In this function, get their response to the yes-or-no question. If they said no,
   return a rendered template, ``goodbye.html``, that tells them goodbye and that they'll
   be missed or something. If they said yes, render a different template, ``game.html``
   that has a simple form that asks for a person, a color, a noun, and an adjective.
   How you choose to implement those inputs are up to you, but you should feel
   free to mix and match. (Hint: it might be fun to try one as a drop-down menu of choices).
   This new form should have the action ``/madlib``.

4. Write a new function, ``show_madlib()``, which is routed to the URL path ``/madlib``.
   It should render the template ``madlib.html``, which should fill in the given-by-user
   person, color, noun, and adjective in a MadLibs-style story.

   Some MadLibs text to get you started:

      There once was a {{ color }} {{ noun }} sitting in the Hackbright Lab.
      When {{ person }} went to pick it up, it burst into flames in a totally
      {{ adjective }} way.

**STOP. Please ask for a code review at this point.**

Extra Credit: Harder
--------------------

1. Change ``game.html`` to have more inputs. Try to use as many different input types
   as you can. Change your ``show_madlib()`` function and ``madlib.html`` template to show
   the new fields in the story.

2. Add some style to your pages. You can use the empty file in ``static/madlibs.css``
   if you'd like.

3. Make a bunch of other Madlib templates and change ``show_madlib()`` to randomly
   choose which one to render.

**STOP. If you get here, please ask for a code review.**

Extra Credit: Even Harder
-------------------------

4. Change the type of request for ``game.html`` submission to ``method="POST"``.
   What other changes in your
   code are needed to make that work? Can you make the same route handle both GET
   and POST? And do something slightly different with each type of request?

5. Modify ``greet_person()`` to pass a list of 3 compliments to ``compliment.html``.
   Modify ``compliment.html`` to display that list using a jinja for loop. Try putting
   that list of compliments in an unordered list. (Hint: there's a very useful function
   in Python's ``random`` module for "make several random selections from a list").

**STOP. If you get here, please ask for a code review.**

Extra Credit: Harder Still
--------------------------

6. We don't want people to be able to submit a MadLib until they've filled out each
   field on their form. Using jQuery, check when they submit a form if they've put something
   into each of the form fields and, if not, present an error message with ``alert()``
   and don't submit the form.

**STOP. If you get here, please ask for a code review.**