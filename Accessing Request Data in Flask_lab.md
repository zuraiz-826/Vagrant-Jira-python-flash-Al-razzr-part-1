Lab 7: Accessing Request Data in Flask
Objectives
Understand how to handle and access different types of request data in a Flask application.
Learn to work with query string parameters and form data.
Use Flask's request object to retrieve data from HTTP requests.
Implement routes to demonstrate reading and responding with request data.
Prerequisites
Basic understanding of Flask framework and Python programming.

Flask installed on your development environment. If not, install Flask using the following command:

pip install flask
A code editor such as Visual Studio Code or PyCharm.

Lab Tasks
Task 1: Setting Up the Flask Application
Create a Project Directory

Create a new directory for your Flask project and navigate into it:

mkdir flask_request_data_lab
cd flask_request_data_lab
Create a Virtual Environment

Set up a virtual environment to manage dependencies:

python -m venv venv
source venv/bin/activate   # On Windows use `venv\Scripts\activate`
Install Flask

Ensure Flask is installed in your virtual environment:

pip install flask
Create the Flask Application

Create a file named app.py and include the following starter code:

from flask import Flask, request

app = Flask(__name__)

@app.route('/')
def home():
    return "Welcome to the Flask Request Data Lab!"

if __name__ == '__main__':
    app.run(debug=True)
Task 2: Accessing Query String Parameters
Define a Route to Access Query Strings

Add a new route in app.py to handle query string parameters:

@app.route('/query')
def query_example():
    # Access query string parameters
    param1 = request.args.get('param1', default='No Param', type=str)
    param2 = request.args.get('param2', type=int)
    return f'Received param1: {param1}, param2: {param2}'
Testing the Query String Route

Run the Flask application:

flask run
Visit http://localhost:5000/query?param1=hello&param2=25 in your web browser to see the output.

Task 3: Accessing Form Data in a POST Request
Create a Form Submission Route

Extend app.py with the following POST route to handle form data:

@app.route('/submit', methods=['POST'])
def form_example():
    # Access form fields
    name = request.form.get('name')
    age = request.form.get('age')
    return f'Received name: {name}, age: {age}'
Create an HTML Form for Testing

Create a file named form.html with the following content:

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Form Example</title>
</head>
<body>
    <form action="http://localhost:5000/submit" method="post">
        <label for="name">Name:</label>
        <input type="text" id="name" name="name"><br><br>
        <label for="age">Age:</label>
        <input type="text" id="age" name="age"><br><br>
        <input type="submit" value="Submit">
    </form>
</body>
</html>
Testing the Form Submission

Open form.html in your web browser.
Fill in the form fields and submit to test data retrieval.
Conclusion
In this lab, we've successfully created a simple Flask application to access and manage request data. By handling both query string parameters and form data, you now have a foundational understanding of working with requests in Flask applications. This knowledge is essential for creating dynamic and responsive web applications that can interact with users effectively.

