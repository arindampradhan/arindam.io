---
layout: post
title: Heroku Unchained
location: Bhubaneswar
tags:
- django
- Heroku
---

I was really excited to try out *heroku*, my *godaddy* webservice sucked. After enabling ssh, it barely managed to give me python2.6.2. Wish I could try old better web platforms.


Anyways, I got to find out some hacks wih heroku which I am going to share.

I will be using django with heroku, post about some ideal settings for heroku that can be used and I found helpful.
Some of the repos I have found helpful [heroku_django_app](https://github.com/heroku/heroku-django-template).
Usually a mini django project format has.
<!--excerpt-->

    your_project
    ├── db.sqlite3
    ├── manage.py
    ├── your_project
    │    ├── __init__.py
    │    ├── settings.py
    │    ├── urls.py
    │    └── wsgi.py
    └── static
        └── templates
            └── signup.html

For **porting** to heroku you can follow [getting_started](https://devcenter.heroku.com/articles/getting-started-with-django), after that the project might look like:

    your_project
    ├── db.sqlite3
    ├── .git
    ├── Procfile
    ├── requirements.txt
    ├── manage.py
    ├── your_project
    │    ├── __init__.py
    │    ├── settings.py
    │    ├── urls.py
    │    └── wsgi.py
    └── static
        └── templates
            └── signup.html

    Procfile
    web: gunicorn your_project.wsgi --log-file -

After adding the required dynos.
A better **settings** can be.

The ``your_project`` can be customized for heroku.

    your_project
    ├── manage.py
    ├── .git
    ├── Procfile
    ├── requirements.txt
    ├── mvp_landing
    │   ├── __init__.py
    │   ├── settings
    │   │   ├── base.py
    │   │   ├── __init__.py
    │   │   ├── local.py
    │   │   └── production.py
    │   ├── settings_old.py
    │   ├── urls.py
    │   └── wsgi.py
    |
    |

* Edit the ``settings.py`` file name to ``settings_old.py``.
* Create a ``settings`` directory. Under this directory create base.py, local.py, production.py.
* The base has the the same code as settings.py but a few things differ such as.

```
    
    BASE_DIR = os.path.dirname(os.path.dirname(__file__))
    to 
    BASE_DIR = os.path.dirname(os.path.dirname(os.path.dirname(__file__)))

```

The ``__init__.py`` file.

    from .base import *

    try:
        from .local import *
        live = False
    except:
        live = True

    if live:memcached
        from .product import *

The ``production.py`` files holds the configuration for heroku:

    # Parse database configuration from $DATABASE_URL
    from django.conf import settings
    import os
    DEBUG = False
    TEMPLATE_DEBUG = True

    import dj_database_url
    DATABASES['default'] = dj_database_url.config()

    # Honor the 'X-Forwarded-Proto' header for request.is_secure()
    SECURE_PROXY_SSL_HEADER = ('HTTP_X_FORWARDED_PROTO', 'https')

    # Allow all host headers
    ALLOWED_HOSTS = ['nameofwebsite.com','herokusite.herokuapp.com']

    # # Static asset configuration (Optional
    # import os
    # BASE_DIR = os.path.dirname(os.path.abspath(__file__))
    # STATIC_ROOT = 'staticfiles'
    # STATIC_URL = '/static/'

    # STATICFILES_DIRS = (
    #     os.path.join(BASE_DIR, 'static'),
    # )

The ``local.py`` file will hold the configuration for local settings the you want to keep like.

    ALLOWED_HOSTS = ['*']

    # Static asset configuration (Optional
    import os
    BASE_DIR = os.path.dirname(os.path.abspath(__file__))
    STATIC_ROOT = 'staticfiles'
    STATIC_URL = '/static/'

    STATICFILES_DIRS = (
        os.path.join(BASE_DIR, 'static'),
    )

Heroku is providing lots of services, especially REDIS and MEMCACHED. We can really built minimal cool apps on top of it.
Will soon update new stuffs with heroku. Long live *heroku*.