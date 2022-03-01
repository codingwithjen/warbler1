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


