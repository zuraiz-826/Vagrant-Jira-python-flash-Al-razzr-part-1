Lab 6: Form Handling (GET & POST)
Objectives
Understand the basics of form handling in web development.
Learn how to create a form and handle data using the GET method.
Learn how to handle form data using the POST method.
Gain skills in rendering and displaying form data on a web application.
Prerequisites
Basic knowledge of HTML for creating forms.
Familiarity with web servers and routing.
Basic understanding of web development using a programming language like Python, with Flask as the web framework, or Node.js with Express.js.
A working development environment with a code editor and a browser.
Lab Setup
Before starting, ensure you have the following software installed:

Flask if you're using Python.
Node.js and Express if you're using JavaScript.
A code editor like Visual Studio Code or Sublime Text.
Lab Tasks
Task 1: Create a Route that Displays a Form Using the GET Method
Step 1.1: Create the Project Folder

Open your terminal or command prompt.

Create a new folder for your project:

mkdir form-handling-lab
cd form-handling-lab
Step 1.2: Set Up Your Flask Application (Python)

Create a new Python file named app.py.

Install Flask using pip:

pip install Flask
Import Flask and set up your basic application:

from flask import Flask, request, render_template

app = Flask(__name__)

@app.route('/form')
def form():
    return '''
        <form method="post" action="/form">
            <label for="name">Name:</label>
            <input type="text" id="name" name="name"><br><br>
            <label for="email">Email:</label>
            <input type="email" id="email" name="email"><br><br>
            <input type="submit" value="Submit">
        </form>
    '''

if __name__ == "__main__":
    app.run(debug=True)
Step 1.2: Set Up Your Express Application (Node.js)

Initialize a new Node.js project:

npm init -y
Install Express.js:

npm install express
Create a new JavaScript file named app.js.

Import Express and set up your basic application:

const express = require('express');
const app = express();
const bodyParser = require('body-parser');

app.use(bodyParser.urlencoded({ extended: true }));

app.get('/form', (req, res) => {
    res.send(`
        <form method="post" action="/form">
            <label for="name">Name:</label>
            <input type="text" id="name" name="name"><br><br>
            <label for="email">Email:</label>
            <input type="email" id="email" name="email"><br><br>
            <input type="submit" value="Submit">
        </form>
    `);
});

app.listen(3000, () => {
    console.log('Server is running on http://localhost:3000');
});
Task 2: Add a Route to Handle Form Submission via POST
Step 2.1: Handle Form Submission in Flask

In the same app.py file, add a POST route to handle the form submission:

@app.route('/form', methods=['POST'])
def form_post():
    name = request.form['name']
    email = request.form['email']
    return f'Name: {name}, Email: {email}'
Step 2.1: Handle Form Submission in Express

In the same app.js file, add a POST route to handle the form submission:

app.post('/form', (req, res) => {
    const name = req.body.name;
    const email = req.body.email;
    res.send(`Name: ${name}, Email: ${email}`);
});
Task 3: Print or Display the Submitted Form Data on the Response
Start your server, and test the form by visiting the /form route.
For Flask:

python app.py
For Express:

node app.js
Fill in the form and check that the data is displayed correctly on submission.
Conclusion
In this lab, you learned how to create a form using both Flask and Express. You explored handling data using both the GET and POST methods, which are fundamental concepts in web development. The skills acquired here allow you to build more complex forms and back-end logic in web applications.

Note: Ensure that you handle form data securely in a real-world application by validating inputs and using secure modules to protect against common vulnerabilities like SQL Injection and XSS (Cross-Site Scripting).

