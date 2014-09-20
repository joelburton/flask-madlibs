MadLibs: A Flask Demo
=====================

In this demo, we'll create a simple Flask application that plays MadLibs.


Setup
-----

1. Create a "virtual environment" so we don't have to install Flask (or other special libraries
   system-wide)::

     virtualenv env

   And start using your virtual environment::

     . env/bin/activate

   (notice the leading dot in that command; it's important)

3. Install Flask::

     pip install Flask

   (this will run for a moment and will download and install several Python libraries)


Running the Application
-----------------------

1. If you haven't done so in this terminal window, start using your virtual environment::

     . env/bin/activate

   (remember, the leading dot in that command is required)

2. Run the application::

     python madlibs.py


Testing the Application
-----------------------

1. Visit http://localhost:5000/hello

   This URL is "routed" to the function ``say_hello()`` and should return "Hello!"

2. Visit http://localhost:5000/compliments

   This is routed to ``say_something_nice()`` and will return a random compliment.

3. Visit http://localhost:5000/

   This URL, "/", is routed to ``show_form()``, and uses the HTML file ``templates/form.html``.
   This is an HTML form with some associated Javascript and CSS that makes it look pretty.

4. Choose a person, enter a color, noun, and adjective,
   and click the "Get MadLib" button. You should get back a plain but working snippet of HTML with
   your results. Notice the URL is something like
   ``/result?person=Cynthia&color=pink&noun=car&adjective=awesome``. This
   URL is routed to ``show_results()``, which gets the values from the request and uses the
   Jinja template in ``templates/result.html`` to display them.

5. Click the "ask for compliments" button. This will return a list of 3 random compliments with
   your MadLib results. In the code, it does this by calling ``choose_compliments()`` and
   returning a random sample.

6. Try using the "get-with-AJAX" button. This uses AJAX (via jQuery) to make the request to
   "/result"--but instead of it appearing as a new browser request, the result of that request
   is loaded into the #madlib-result div. You can see the jQuery code for this in the
   ``form.html`` file.
