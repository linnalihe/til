https://flask.palletsprojects.com/en/2.3.x/

#### Installation
Go to [Postgres app download page](https://postgresapp.com/downloads.html) and download postges.app if on MacOS

Go to [Pgadmin](https://www.pgadmin.org/), go to download page for your system and download PgAdmin - this is optional but will let you look at your data in a Graphical User Interface aka GUI; can also use others such as Postico or DBeaver

Download Postman from https://www.postman.com/downloads/
When requesting from Postman, make sure that the 'Content-Type' and and 'Accept' is set to `application/json`

Download and open VSCode
Create an empty folder and open in VSCode
Set up python environment with pyenv
Install with pip
`pip install flask, flask-sqlalchemy` ... etc

#### Project creation and stand up DB
Create an app.py file (this is the main file that you need)

Database operations can be done locally for testing and development; Use migrations should be used for operating on production database

DELETE or CREATE a database by opening the terminal and using SQL command after going into database process with `psql` , or another option is to run `db` commands in a shell environment shown below 

When performing operations in shell environment you will need to be within the app context

1. Run via flask shell
```bash
$ flask shell
>>> db.drop_all()
>>> db.create_all()
```

2. Push a app context manually
```bash
$ python3
>>> from project import app, db
>>> app.app_context().push()
>>> db.create_all()
```

3. Basic template
```python
from flask import Flask, request

from flask_sqlalchemy import SQLAlchemy


app = Flask(__name__)

DATABASE_URL="postgresql:///your-db"

app.config['SQLALCHEMY_DATABASE_URI'] = DATABASE_URL

db = SQLAlchemy(app)

@app.route("/home", methods=['GET'])
def home():
	return "hello world!"

  
@app.route("/message", methods=['POST'])
def message():
	data = request.json
	first = data.get('first')
	last = data.get('last')
	return f'hi {first} {last}'
  
if __name__ == '__main__':

app.run()
```


