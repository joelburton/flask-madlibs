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

2. Run the application::

     python madlibs.py


Testing the Application
-----------------------

1. Visit http://localhost:5000/

   This URL is "routed" to the function ``start_here()`` and returns a simple string:
   "Hello!"

2. Visit http://localhost:5000/hello

   This is routed to ``say_hello()`` and will show you a simple form and ask
   your name. It is rendering a template called ``templates/hello.html``.

3. Submit the form. This will send you to http://localhost:5000/greet?person={your name here}

   This URL, "/greet", is routed to ``greet_person()``. This page is getting the
   name entered in the previous form via ``reqeust.args.get(person)``, choosing a
   random compliment, and passing both the person variable and the compliment
   to the HTML file ``templates/compliment.html``.

Your Task
---------

Now that we've got a solid foundation for our first webapp, let's have some fun.

1. Modify the template ``compliment.html`` to ask the person if they'd like to play
   a game (hint: try a radio button!). Route the sumbission of this form to ``/game``.

2. If they say no, take them to a page that tells them goodbye and that they'll
   be missed or something. If they say yes, take them to a page called ``game.html``
   that has a simple form that asks for a person, a color, a noun, and an adjective.
   How you choose to implement those inputs are up to you, but you should feel
   free to mix and match.

3. Submitting the form on ``game.html`` should take you to a new route,
   ``/madlib``, that renders the template ``madlib.html``

   Some madlib text to get you started:

      There once was a {{ color }} {{ noun }} sitting in the Hackbright Lab.
      When {{ person }} went to pick it up, it burst into flames in a totally
      {{ adjective }} way.


More fun with Madlibs
---------------------

1. Modify ``greet_person()`` to pass a list of compliments to ``compliment.html``.
Modify ``compliment.html`` to display that list using a jinja for loop. Try putting
that list of compliments in an unordered list.

2. Change the type of request to a ``method="POST"``. What other changes in your
code are needed to make that work? Can you make the same route handle both GET
and POST? And do something slightly different with each type of request?

3. Add some style to your pages. You can use the empty file in ``static/madlibs.css``
if you'd like.

4. Change ``game.html`` to have more inputs. Try to use as many different input types
as you can.

5. Make a bunch of other Madlib templates and change ``/madlib`` to randomly
choose which one to render.

6. Use jQuery to add a bunch of buttons to ``game.html``. Each button should take
you to a different Madlib. Can you do this with only one route?

