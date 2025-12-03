Lab Name: 2. Understanding Basic Flask Routes
Objectives
Understand the basic role of routes in a Flask application.
Learn how to define routes using Flask's @app.route decorator.
Implement multiple routes and test their responses.
Print log statements to view console output for debugging and learning.
Prerequisites
Basic knowledge of Python programming.
Python environment set up on your local machine.
Flask installed (pip install flask).
Text editor or IDE like VSCode, PyCharm, etc.
Introduction to Flask Routes
Flask routes determine how your web application responds to different requests from the client on specific URLs. They form the core navigation mechanism of a Flask application. Routes use decorators to register URLs with specific functions in your codebase.

Lab Tasks
1. Setting up a Basic Flask Application
1.1. Create Your Flask Project
Open a terminal and create a new directory for your Flask project.
mkdir flask_routes_lab
cd flask_routes_lab
Create a new Python script, app.py, in this directory.
touch app.py
1.2. Setting up Flask in your Python Script
Open app.py in your text editor and add the following:
from flask import Flask

app = Flask(__name__)

if __name__ == '__main__':
    app.run(debug=True)
Explanation:
Flask Instance: We create an instance of the Flask class. This instance will be our WSGI application.
Debug Mode: Running the app with debug=True enables the debugger and autoreload modes for your Flask server.
2. Creating Basic Routes
2.1. Create a Default Route
Add the following code in app.py to define a route for the homepage:
@app.route('/')
def home():
    print("Rendering Home Page")
    return 'Welcome to the Home Page!'
Explanation:
@app.route('/'): This specifies that the function directly below handles requests to the root URL ('/').
2.2. Add Another Route
Create an additional route /about by adding the following code:
@app.route('/about')
def about():
    print("Rendering About Page")
    return 'This is the About Page.'
Explanation:
Multiple Routes: We are defining another route for /about which returns a different message.
3. Testing Routes
3.1. Run the Flask Application
Start the Flask server by running:
python app.py
Open your web browser and visit http://127.0.0.1:5000/ to see the home page.

Visit http://127.0.0.1:5000/about to test the about page.

Console Output: Check your terminal for the print statements each time you navigate to a route.

4. Logging and Debugging
4.1. Print Log Statements
Ensure each route has a print statement for logging, already shown in the code snippets above.

Console Observations: Observe the Flask terminal for printed messages confirming which route was accessed. This helps in debugging.

Conclusion
In this lab, you learned to set up basic Flask routes and explored how to direct requests to different endpoints in a Flask application using the @app.route decorator. You created multiple routes, tested their functionality in a browser, and employed log statements for simple debugging techniques. Understanding these concepts is fundamental in designing web applications with Flask, ensuring structured navigation and user interaction pathways.

