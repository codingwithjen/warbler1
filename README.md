# Warbler App
## Twitter Clone - Springboard's Software Engineer Program
Twitter is one of the most widely used apps in the world, also known for its distinctive Tweets. This exercise is intended to extend a somewhat-functioning Twitter clone. Our Twitter Clone will be called Warbler!
### Goals:
- Read and understand an existing application
- Fix bugs and write tests for application
- Extend the application with new features
***
## 1. Set-Up
Create the Python virtual environment:
```
$ python3 -m venv venv
$ source venv/bin/activate
(venv) $ pip install -r requirements.txt
```
It is important to note that if you're using Python v.3.8 instead of v.3.7, you will run into problems. Please *delete* `psycopg2-binary` from the **requirements.txt** file if you are on v.3.8 and don't forget to `pip3 install psycopg2-binary` AFTER running the requirements.txt file. Shortly afterwards, please `pip3 freeze > requirements.txt` to update and save the requirements.txt file, with psycopg-binary installed.
## 2. Setting up the database:

```
(venv) $ createdb warbler
(venv) $ python seed.py
```

## 3. Start the server:
```
(venv) $ flask run
```

## 4. Part One, Step Seven: Research and Understand Login Strategy:

- **How is the logged in user being kept track of?**
    - The logged in user is being kept track of with *Flask Sessions.* Session is the time interval when a client logs into a server and logs out of it. The data, which is needed to be held across the session, is stored in the client browser. A session with each client is assigned a *Session ID*.

- **What is Flask's g object?**
    - *g* is an object provided by Flask. It's a global namespace for holding any data you want during a single app context. In other words, it makes data global across your Flask app. You can use that data in other locations rather than if it's stored in a `.py` file.

- **What is the purpose of add_user_to_g?**
    - The purpose of `add_user_to_g` is to keep track of the logged in user on the Flask application. If the session of the logged in user is stored, then the current user is stored to the Flask global **g**, which will be accessible to the route and other functions being referenced and used by the g-object.

- **What does @app.before_request mean?**
    - This handler allows us to execute a function *before* any request.

- **Source Links:**
    - [Source 1](https://www.py4u.net/discuss/12919)
    - [Source 2](https://www.tutorialspoint.com/flask/flask_sessions.htm)


## 5. Part Three, Add Tests:
To run a file that contains unittests, you can run the command `FLASK_ENV=production python -m unittest <name-of-python-file>`
> Remember to createdb for warbler-test to complete testing