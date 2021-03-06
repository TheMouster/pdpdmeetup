Python 2
========

This project runs Python 2 because it's an old project and also to annoy some people.

requirements.txt
================

requirements.txt is for Heroku. If you try to `pip install -r requirements.txt` for local development you may get the following error caused by installing `psycopg`:

    Collecting psycopg2==2.6.1 (from -r requirements.txt (line 6))
      Using cached https://files.pythonhosted.org/packages/86/fd/cc8315be63a41fe000cce20482a917e874cdc1151e62cb0141f5e55f711e/psycopg2-2.6.1.tar.gz
        Complete output from command python setup.py egg_info:
        running egg_info
        creating pip-egg-info/psycopg2.egg-info
        writing pip-egg-info/psycopg2.egg-info/PKG-INFO
        writing top-level names to pip-egg-info/psycopg2.egg-info/top_level.txt
        writing dependency_links to pip-egg-info/psycopg2.egg-info/dependency_links.txt
        writing manifest file 'pip-egg-info/psycopg2.egg-info/SOURCES.txt'
        Error: could not determine PostgreSQL version from '10.4'

        ----------------------------------------
    Command "python setup.py egg_info" failed with error code 1 in /tmp/pip-install-FRFq2C/psycopg2/

That's why you use `requirements-dev.txt` for local development.


Perth Django and Python Developers
==================================

A home for the Perth Django and Python community. 

Please check out our [Meetup.com group page](http://www.meetup.com/Perth-Django-Users-Group/) for more details

And our [Slack Channel](https://pdpdmeetup-slack.herokuapp.com/)

Deployment
==========

https://devcenter.heroku.com/articles/getting-started-with-python#set-up

Install Heroku Client to get the `heroku` command:

- https://devcenter.heroku.com/articles/heroku-cli

Login to Heroku with Toolbelt:

- `heroku login`

Clone pdpdmeetup repository:

- `git clone https://github.com/mattharley/pdpdmeetup.git`

Add heroku remote URL:

- `cd pdpdmeetup`
- `git remote add heroku https://git.heroku.com/pdpdmeetup.git`

Deploy! (Probably fail if you don't have permission on Heroku, please ask Matt for access)

- `git push heroku master`


Other useful info (especially for beginners)
============================================

Indent standard = 4 spaces

`project root` - This is the folder where all files relating to the project and its apps are stored.
Path = `/pdpdmeetup/`

`project app` - This is the core app for the project. Essentially its just the first app that got created and often contains core logic or shared files such as common templates.
Path = `/pdpdmeetup/pdpdmeetup/`

Templates are split into two locations.

1. Project templates which are shared amongst all apps are stored under the `project app`'s templates folder
Path = `/pdpdmeetup/pdpdmeetup/templates`

2. App templates which are app specific (where `app1` is the app name)
Path = `pdpdmeetup/app1/templates`

