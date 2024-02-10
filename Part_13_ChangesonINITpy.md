# Custom Snippet for Flask Application Setup in __init__.py

To initialize your Flask application with MySQL database configuration, including setting the cursor class to `DictCursor`, add the following code snippet to your `__init__.py` file:

```json
{
  "Flask Application Setup with MySQL": {
    "prefix": "flaskAppSetupMySQL",
    "body": [
      "from flask import Flask",
      "from flask_mysqldb import MySQL",
      "",
      "app = Flask(__name__)",
      "",
      "app.secret_key = 'quiz_app'",
      "",
      "# Configure the database",
      "app.config['MYSQL_HOST'] = 'localhost'",
      "app.config['MYSQL_USER'] = 'root'",
      "app.config['MYSQL_PASSWORD'] = ''",
      "app.config['MYSQL_DB'] = 'quizgamedb'",
      "app.config['MYSQL_CURSORCLASS'] = 'DictCursor'",
      "",
      "mysql = MySQL(app)",
      "",
      "from quizapp.routes import *"
    ],
    "description": "Initializes the Flask application and configures the MySQL database connection with a dictionary cursor for easier data manipulation."
  }
}
