Title: Learning-pelican
Date: 2020-07-05 12:40
Status: published
Category: python
Tags: python, blogging, pelican
Slug: Fourth-Post
Authors: Abdul Sayyed
Summary: Learning pelican static site generator


## What are we using to build a site.

1. Pelican library installed with 
2. Markdown parsing library
3. Jinja2, a template engine
4. pip or conda virtual environment that a user create where the above are installed and kept serprately.
5. Other buildig tools
    1. [Flask tutorial](https://blog.miguelgrinberg.com/). A web framework.
    2. [Green unicorn or gunicorn](https://www.fullstackpython.com/green-unicorn-gunicorn.html) is web server Gateway implementation (WSGI) tha tis used to run Python web aaplication.
    3. [Jinja2](https://www.fullstackpython.com/jinja2.html). An implementation of a template engine.This link contains many useful sites.


## What guides are available to use.

1. [Full Stack Python](https://www.fullstackpython.com/blog/python-3-flask-green-unicorn-ubuntu-1604-xenial-xerus.html)
2. 


### Building a Basic site.

1. Select your working director, or cd into it.
2. Create a virtual env, if not created. Activate your environment
3. Install pelican and markdown parsing  libraries with pip ,e.g., `pip install pelican==3.7.1 markdown==2.6.8`
    - Installing pelican would install `feedgenerator, jinja2, pygments, docutils, pytx, blinker and unidecode`
    - Optionally you can install using pip other librarirs lke `piloow, beautifulsoup4, cssmin, cssprefixer, cssutil, pretty, six, smartypans and typogrify webassets`
    
4. Start pellican `pelican-quickstart`
5. Following files are created.
    
```py
Makefile          pelicanconf.py
content/           publishconf.py
``` 

  - make command is used to genereat/start many task such as , making html, cleaning, regenerating serving etc. It is generated according to the input which we have used while creating a basic infrasturcture.
  - content/ directory is used to write markdown contents wile other two files are for configuation.

6. Run `make html` and the contents of our markdown file will be converted into html in a newly created directory called `output`
7. Run `make serve` and server will start on a local host post on port 8000.
8. You can also use `pelican -s pelicanconf.py -o output content` to make html instead of make html
9. You can cd to ouput then use `python -m http.server`
10. Write your post in **content/** directory using post or blog or any other directory like **code/** etc and keep your post or articles seprate.
11. If using sublime use this [package] `https://packagecontrol.io/packages/Pelican`. Once installed use `Ctr+shift+p` and write `pelican` help wil come. You can cofigure the metadata.

### Add themes




### Customising the views

- New custom `.css` and `.js` files are added in a new folder under `content\extra`.
- We need to tell `pelicanconf.py` where are they stroed.
- Add the following contents in the config file

```py
pelicanconf.py

CUSTOM_CSS = 'static/css/custom.css'
CUSTOM_JS = 'static/js/custom.js'

STATIC_PATHS = [ 'extra' ]

EXTRA_PATH_METADATA = {
    'extra/custom.css': {'path': 'static/css/custom.css'},
    'extra/custom.js': {'path': 'static/js/custom.js'}
}


```

### Adding pages to the site 

- Pages are not post but about you or the sites.
- Create a new folder under `content/pages` and add a new file called `about.md`.
- Tell config file about the pages, add the following to your config file

```
# Paths
PATH = 'content'
PAGE_PATHS = ['pages']
ARTICLE_PATHS = ['posts']

# Top menus
DISPLAY_CATEGORIES_ON_MENU = False
DISPLAY_PAGES_ON_MENU = True

```





