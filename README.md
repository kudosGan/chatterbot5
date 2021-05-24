# chatterbot5
flask-chatterbot
A web implementation of ChatterBot using Flask.
Local Setup:
Ensure that Python, Flask, SQLAlchemy, and ChatterBot are installed (either manually, or run pip install -r requirements.txt).
Run app.py
Demo will be live at http://localhost:5000/
How do I deploy this to a web server?
If you do not have a dedicated server, I highly recommend using PythonAnywhere, AWS or Heroku to host your application.

Deploying on PythonAnywhere
Here is a quick 5 minute video on how to get setup: https://youtu.be/VP0HvbunaRo

Deploying on Heroku
If you are deploying on Heroku, you will have to change the database adapter from chatterbot.storage.SQLStorageAdapter to chatterbot.storage.MongoDatabaseAdapter since SQLite3 isn't supported. To do this simply change the following line:

english_bot = ChatBot("English Bot", storage_adapter="chatterbot.storage.SQLStorageAdapter")

... to use the MongoDB adapter:

english_bot = ChatBot("English Bot", 
                     storage_adapter = "chatterbot.storage.MongoDatabaseAdapter",
                     database = mongodb_name,
                     database_uri = mongodb_uri)
... where mongodb_name is the name of the database you wish to connect to and mongodb_uri is the URI of a remote instance of MongoDB.

License
This source is free to use, but ChatterBot does have a license which still applies and can be found on the LICENSE page.
