Lab Name: 9. Flash Messages
Objectives:

Understand the concept of flash messages in Flask applications.
Learn to configure and use flash messages to enhance user interaction.
Implement success and error message notification using flask.
Prerequisites:

Basic knowledge of Python programming.
Familiarity with Flask web framework.
Understanding of HTML and Jinja2 templating.
Introduction
Flash messages in Flask provide a convenient way to send notifications to users regarding the status of their actions. These are typically used to inform users about the success or failure of their interactions with the web application.

Task 1: Import and Configure Flash in Flask
Import Flask and Flash

Begin by importing the necessary modules in your app.py:

from flask import Flask, flash, render_template, redirect, url_for
Configure the Secret Key

Set a secret key for your Flask app which is essential for using flash messages:

app = Flask(__name__)
app.config['SECRET_KEY'] = 'random-secret-key'
Key Concept: The SECRET_KEY is used by Flask to encrypt session cookies and ensure data integrity. It is crucial for security, especially when using features like session and flash messages.
Task 2: Implement Flash Messages Upon Form Submission
Create a Simple HTML Form

Let's create a simple form in templates/form.html:

<form action="{{ url_for('submit') }}" method="post">
    <input type="text" name="user_input" placeholder="Enter something" required>
    <button type="submit">Submit</button>
</form>
Route to Handle Form Submission

In your app.py, create a route to handle this form submission:

@app.route('/submit', methods=['POST'])
def submit():
    user_input = request.form.get('user_input')
    if user_input:
        flash("Successfully received input!")
        return redirect(url_for('index'))
    else:
        flash("Input is required!", "error")
        return redirect(url_for('index'))
Key Concept: flash() is used here to store a message that can be retrieved on rendering the next view.
Technical Note: Messages are stored in a session, requiring the SECRET_KEY.
Task 3: Displaying Flash Messages in Templates
Display Flash Messages in HTML Template

Update your index template (e.g. templates/index.html) to display flashed messages:

{% with messages = get_flashed_messages(with_categories=true) %}
    {% if messages %}
        <ul>
            {% for category, message in messages %}
                <li class="{{category}}">{{ message }}</li>
            {% endfor %}
        </ul>
    {% endif %}
{% endwith %}
Key Concept: get_flashed_messages() retrieves all flashed messages, which can then be looped over and displayed accordingly.
Style the Flash Messages (Optional)

Use CSS to style your flash messages by categories:

.error {
    color: red;
}

.message {
    color: green;
}
Conclusion
In this lab, you've learned to effectively use flash messages in a Flask web application to inform users about their actions. Flash messages are a powerful feature for improving user experience by providing immediate feedback, thus enhancing the overall quality of your web application.

You should now feel comfortable integrating flash messaging in your Flask applications to handle basic user notifications. Further exploration could involve customizing the appearance of these messages to align with your webpage's design and learning about more advanced message handling techniques in Flask.

