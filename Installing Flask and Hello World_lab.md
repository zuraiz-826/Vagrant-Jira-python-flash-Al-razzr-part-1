Lab Name: Installing Flask and Hello World
Lab Objectives:

To understand how to create and manage a Python virtual environment.
To learn the installation process of Flask using the Python package manager pip.
To construct a basic Flask web application.
To run the Flask application and verify its functionality in a web browser.
Prerequisites:

Basic understanding of Python programming.
Python installed on your system (preferably Python 3.6 or later).
Fundamental knowledge of web servers and HTTP protocols.
Lab Tasks:

Task 1: Setting Up a Python Virtual Environment
Step 1.1: Create a New Virtual Environment
A virtual environment is a self-contained directory that hosts Python projects and their dependencies. This ensures that dependencies are isolated from other projects.

Open your terminal or command prompt.

Navigate to the directory where you want to create your project.

cd path/to/your/project/directory
Create a virtual environment using the following command:

python -m venv env
Activate the virtual environment:

On Windows:

.\env\Scripts\activate
On macOS/Linux:

source env/bin/activate
Step 1.2: Verify Activation
Check if your command prompt has been prefixed by (env), indicating that the virtual environment is active.

Task 2: Installing Flask
Step 2.1: Install Flask using pip
With the virtual environment active, install Flask using the following command:

pip install flask
Step 2.2: Confirm Flask Installation
Verify the installation by running:

pip show flask
This command displays the version and other package information, ensuring Flask is successfully installed.

Task 3: Creating a Basic Flask Application
Step 3.1: Write a Minimal Flask Application
Create a new file named app.py in your project directory and add the following code snippet:

from flask import Flask

app = Flask(__name__)

@app.route('/')
def hello_world():
    return 'Hello, World!'
Key Concepts:
Flask instance: Flask(__name__) initializes your app.
Route decorator: @app.route('/') maps the URL path '/' to the hello_world function.
Task 4: Running and Testing the Flask Application
Step 4.1: Run the Flask Application
Start the Flask server by executing the following command in your terminal:

flask run
Ensure the environment variable FLASK_APP is set to app.py. If not, set it using:

On Windows:

set FLASK_APP=app.py
On macOS/Linux:

export FLASK_APP=app.py
Step 4.2: Test in Your Browser
Open a web browser and go to http://127.0.0.1:5000. You should see "Hello, World!" displayed.

Conclusion:
In this lab, you have successfully set up a Python virtual environment, installed the Flask web framework, created a simple "Hello World" application, and verified its functionality in a web browser. This foundational knowledge provides a stepping stone for developing more complex Flask applications in future labs.

