Lab Name: Template Inheritance
Lab Objectives:

Understand the concept of template inheritance in web development.
Learn how to create a base HTML template with common blocks.
Implement a child template that inherits and extends a base template.
Confirm the rendering of child templates within the specified layout.
Prerequisites:

Basic understanding of HTML and CSS.
Familiarity with web templating concepts (e.g., Jinja2 for Flask or Django Templates).
A working knowledge of a web development framework such as Django or Flask.
Overview: Template inheritance allows you to create a skeletal HTML structure, defining common features and sections that can be shared across different templates in your application. This encourages DRY (Don’t Repeat Yourself) principles by allowing individual pages to extend the base template and override specific sections when necessary.

LAB TASKS
Task 1: Create a Base HTML Template
Prepare Your Development Environment

Ensure you have a functioning Flask or Django project set up in your development environment.
If using Django, ensure your app is integrated into the INSTALLED_APPS setting and templates are properly connected.
Create the base.html Template

In the templates directory of your project, create a new file named base.html.
Define the basic structure of your HTML document, including <html>, <head>, and <body> tags.
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>{% block title %}Welcome{% endblock %}</title>
</head>
<body>
    <header>
        <h1>My Website</h1>
        <nav>
            <!-- Navigation Links -->
        </nav>
    </header>
   
    {% block content %}
    <!-- Content will be provided by extending templates -->
    {% endblock %}
   
    <footer>
        <p>&copy; 2023 My Website</p>
    </footer>
</body>
</html>
Key Concepts:

Blocks: Blocks are placeholders for content that can be overridden in child templates. Here, we have defined a title and a content block.
Task 2: Create a Child Template
Create a New Template File

In the templates directory, create a new file named child.html.
Extend the Base Template

Use the {% extends %} tag to inherit from base.html.
{% extends "base.html" %}

{% block title %}Child Page{% endblock %}

{% block content %}
    <h2>Welcome to the Child Page</h2>
    <p>This is additional content specific to the child template.</p>
{% endblock %}
Key Concepts:

Extending Templates: The {% extends %} tag is used to indicate that this template should inherit from base.html.
Overriding Blocks: The {% block %} and {% endblock %} tags in child.html override the respective blocks defined in the base.html.
Task 3: Render the Child Template
Set Up Your View Function

For Flask, create a view function in app.py:
from flask import Flask, render_template

app = Flask(__name__)

@app.route('/')
def home():
    return render_template('child.html')

if __name__ == "__main__":
    app.run(debug=True)
For Django, update your views in views.py:
from django.shortcuts import render

def home(request):
    return render(request, 'child.html')
Launch Your Web Application

Run your Flask or Django server and navigate to the root URL (e.g., http://127.0.0.1:5000/ for Flask).
Expected Outcome: Verify that the child template child.html is rendered with the content and header/footer from the base.html.

Conclusion: Upon completion of this lab, you should have a clear understanding of how to implement template inheritance using blocks to separate and override content in web applications. This technique is vital for efficiently managing common layouts and ensuring consistency across your web pages. By mastering template inheritance, you optimize code readability and maintainability while adhering to DRY principles.

