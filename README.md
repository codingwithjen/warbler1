# Warbler App
### Twitter Clone
#### Springboard's Software Engineering Program
This exercise is intended to extend a somewhat-functioning Twitter clone
***
### Setup
Create the Python virtual environment:
```
$ python3 -m venv venv
$ source venv/bin/activate
(venv) $ pip install -r requirements.txt

Important Note:
If you are using Python 3.8 instead of 3.7, then you will have issues with installing some of the packages in the
requirements.txt file into your virtual environment.
For Python 3.8 students, we recommend deleting pyscopg2-binary from the requirements.txt file,
and using pip install pyscopg2-binary in the terminal
in order to successfully install this package.
```


Set up the database:
```
(venv) $ createdb warbler
(venv) $ python seed.py
```

Start the server:
```
(venv) $ flask run
```

#### Part One, Step Seven: Research and Understand Login Strategy

- **How is the logged in user being kept track of?**
    - The logged in user is being kept track of with *Flask Sessions.* Session is the time interval when a client logs into a server and logs out of it. The data, which is needed to be held across the session, is stored in the client browser. A session with each client is assigned a *Session ID*. The Session data is stored on top of cookies and the server signs them cryptographically. For this encryption, a Flask application needs a defined **SECRET_KEY**.

- **What is Flask's g object?**
    - *g* is an object provided by Flask. It's a global namespace for holding any data you want during a single app context. In other words, it makes data global across your Flask app. You can use that data in other locations rather than if it's stored in a .py file.

- **What is the purpose of add_user_to_g?**
    - The purpose of add_user_to_g is to keep track of the logged in user on the Flask application. If the session of the logged in user is stored, then add the current user is stored to the Flask global **g**, which will be accessible to the route and other functions being referenced and used by the g-object.

- **What does @app.before_request mean?**
    - This handler could set g.user, which will be accessible to the route and other functions.

- **Source Links:**
    - [Source 1](https://www.py4u.net/discuss/12919)
    - [Source 2](https://www.tutorialspoint.com/flask/flask_sessions.htm)


#### Part Three, Add Tests
To run a file contain unittests, you can run the command `FLASK_ENV=production python -m unittest <name-of-python-file>`
> Remember to createdb for warbler-test to complete testing