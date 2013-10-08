
Build a Simple Web App
======================

Build and deploy a simple web app using Flask, git, Heroku, and python. For the
purposes of this walkthrough, the app name will be my-webapp.

### Preconditions

1. Install python
2. Install virtualenv
3. Install git
4. Install Heroku Toolbelt and create account with ssh key
5. Create a Github account with ssh key (optional)

### Step 1: Create directories and empty files

Your files should end up with the following structure:

```
/my-webapp
    /.git
    .gitignore
    Procfile
    webapp.py
    requirements.txt
    /static
        style.css  # Example static file for CSS
    /templates
        base.html  # Example template file for a base HTML page
```

~$ mkdir my-webapp
~$ cd my-webapp
~/my-webapp$ mkdir static templates
~/my-webapp$ touch webapp.py static/style.css templates/base.html

### Step 2: Initialize virtual environment and git repo

After creating a virtual environment and git repo, a simple `.gitignore` file is
created using the unix/linux command line. This can also be done by editing
`.gitignore` with any text editor.

~/my-webapp$ echo "Virtual Environment"
~/my-webapp$ virtualenv venv
~/my-webapp$ . venv/bin/activate
(venv)~/my-webapp$ pip install Flask gunicorn

(venv)~/my-webapp$ echo "git Repo"
(venv)~/my-webapp$ git init
(venv)~/my-webapp$ echo "*.py[cod]" > .gitignore
(venv)~/my-webapp$ echo "/venv" >> .gitignore
(venv)~/my-webapp$ cat .gitignore
*.py[cod]
/venv

### Step 3: Make web app Heroku-aware

A simple `Procfile` file is created using the unix/linux command line. This can
also be done by editing `Procfile` with any text editor.

(venv)~/my-webapp$ heroku login
username:
password:
(venv)~/my-webapp$ heroku create my-webapp
(venv)~/my-webapp$ echo "web: gunicorn webapp:app" > Procfile
(venv)~/my-webapp$ pip freeze > requirements.txt

### Step 4: Make web app Github-aware (optional)

The remote repo must be created at Github through the web interface before this
will work.

(venv)~/my-webapp$ git remote add origin git@github.com:username/my-webapp.git

### Step 5: Edit `webapp.py` to add python code

This small app has a basic homepage, with the classic content.

```
from flask import Flask

app = Flask(__name__)

@app.route('/')
def index():
    return 'Hello, World!'

# Include a module runner to allow local testing
if __name__ == '__main__':
    app.run(debug=True)  # Set to false for production
```

### Step 6: Deploy web app to Heroku and/or Github

(venv)~/my-webapp$ echo "Update local repo"
(venv)~/my-webapp$ git add .
(venv)~/my-webapp$ git commit -m 'Intial commit.'

(venv)~/my-webapp$ git push heroku master

(venv)~/my-webapp$ git push origin master
