How to extend flaskr
====================

1. Clone full flask repo
2. Isolate flaskr sample and initialize repo
3. Add GitHub remote and sync
4. Create and gitignore virtual environment
5. Install Flask

```
    git clone https://github.com/mitsuhiko/flask.git
    mv flask/examples/flaskr/ .
    rm -Rf flask
    cd flaskr
    git init
    git add .
    git commit -m 'Clone from public repo.'
    git remote add origin git@ocprof:oc-cs470/new-flasker.git
    git pull -u origin master
    git push
    virtualenv venv
    vi .gitignore (to add venv)
    git add .gitignore
    git commit -m 'Ignore the virtual environment directory.'
    git push
    . venv/bin/activate
    pip install Flask
    python flaskr.py &
```
