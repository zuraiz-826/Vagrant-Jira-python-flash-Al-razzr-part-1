Lab 4: Flask Templates with Jinja2
Objectives
Understand the basics of Flask web framework and its integration with Jinja2 templates.
Learn how to create templates and pass variables from Flask routes to templates using Jinja2 syntax.
Develop a simple web page displaying dynamic data.
Prerequisites
Before beginning this lab, ensure you have the following:

Basic understanding of Python programming.
Flask installed (pip install Flask).
Familiarity with HTML.
A code editor and terminal access.
Lab Tasks
Task 1: Set Up Flask Framework
Install Flask

Open your terminal and execute the following command:

pip install Flask
Create the Project Structure

Organize your project in a manner that follows Flask conventions:

/flask_app/
    ├── app.py
    └── templates/
        └── index.html
app.py: The main Python file to run the Flask application.
templates/: Directory to store HTML templates.
Task 2: Create Flask Application
Initialize a Flask App

In app.py, write the code to create a basic Flask application:

from flask import Flask, render_template

app = Flask(__name__)

@app.route('/')
def home():
    return render_template('index.html')

if __name__ == '__main__':
    app.run(debug=True)
@app.route('/'): Defines the home URL.
render_template('index.html'): Links the route to the HTML file.
Run the Flask Application

Start your application by executing:

python app.py
Open a web browser and go to http://127.0.0.1:5000/ to see the initial setup.

Task 3: Create and Use a HTML Template
Create index.html Template

Navigate to the templates/ folder and create index.html:

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Flask with Jinja2</title>
</head>
<body>
    <h1>Welcome to Flask with Jinja2</h1>
    <p>{{ message }}</p>
</body>
</html>
{{ message }}: Jinja2 syntax for variable substitution.
Task 4: Pass Data to Templates
Modify the Flask Route to Pass a Variable

In app.py, update the home function to pass data:

@app.route('/')
def home():
    message = "Hello, welcome to the Flask Lab!"
    return render_template('index.html', message=message)
message=message: Passes Python variables to the template.
Task 5: Access Dynamic Content
Test Dynamic Content

Refresh your web browser. Verify that the index.html page now displays: "Hello, welcome to the Flask Lab!"

Conclusion
In this lab, you successfully created a basic Flask application, used Jinja2 templates for HTML rendering, and learned to pass and display variables dynamically. These foundational techniques are crucial for building more complex Flask applications that interact with users and databases. Through this exercise, you acquired practical knowledge in linking Python logic with front-end presentation using Flask and Jinja2.

Ensure to explore more on conditional rendering, loops, and block inheritance within Jinja2 to further enhance your template development skills.

