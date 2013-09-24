Working with Flask-OAuth Examples
=================================

Step-by-step
------------

    git clone https://github.com/mitsuhiko/flask-oauth.git
    cd flask-oauth/
    virtualenv venv
    . venv/bin/activate
    pip install Flask
    pip install Flask-OAuth
    pip install sqlalchemy  # Needed for twitter example
    python tweet.py     # Some error in SQLalchemy
    python facebook.py  # Needs some editing for consumer id/secret
    python google.py    # Needs some editing for consumer id/secret

