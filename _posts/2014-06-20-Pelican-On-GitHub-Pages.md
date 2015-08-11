---
layout: post
title:  "How to setup Pelican Blog Hosted on GitHub Project Pages"
date:   2014-06-20 14:48:00
categories: technical
author:  Anna Lukasiak
---

This blog post documents the setup done to create [Data Gallery Blog](http://datagallery.io/pelican) and instructions on how to create and add a new post.

Instructions used to create the Data Gallery Blog can be found on [Pelican on Github Pages](http://docs.getpelican.com/en/3.3.0/tips.html#publishing-to-github) and [Pelican Documentation](http://docs.getpelican.com/en/3.3.0/).  They include configuration options, plug-ins and theming not included in this post.

Installing Python
-----------------
Pelican currently runs best on Python 2.7.x, earlier versions are not supported and it's not yet fully tested on Python 3.3.  To confirm if you have the required Python 2.7.x version, open up the Terminal application, and run:

	python --version

If you have older version, follow [these instructions](https://www.python.org/download/releases/2.7) to install Python.

Installing Pelican
------------------
The recommended approach is to create a virtual environment for Pelican via [virtualenv](https://virtualenv.pypa.io/en/latest/) before installing Pelican. Assuming you have virtualenv installed, you can then open a new Terminal session and create a new virtual environment for Pelican.  You can skip this step if you do not wish to user virtual environment.

	virtualenv ~/virtualenvs/pelican
	cd ~/virtualenvs/pelican
	. bin/activate

Once the virtual environment has been created and activated, Pelican can be be installed via pip.

	pip install pelican

Instructions to install pip are [here](http://pip.readthedocs.org/en/latest/installing.html).

Creating new blog site
----------------------
Now that you have Pelican installed, you can create a skeleton site via the interactive pelican-quickstart command, which will ask you few questions and pre-populate configuration files based on your ansewers.  If not sure about some of the answers, use defaults.

	pelican-quickstart

Those are the questions included for Pelican v3.3.0:

	Welcome to pelican-quickstart v3.3.0.

	This script will help you create a new Pelican-based website.

	Please answer the following questions so this script can generate the files
	needed by Pelican.

	    
	> Where do you want to create your new web site? [.] 
	> What will be the title of this web site? Data Gallery Blog
	> Who will be the author of this web site? Anna Lukasiak
	> What will be the default language of this web site? [en] 
	> Do you want to specify a URL prefix? e.g., http://example.com   (Y/n) 
	> What is your URL prefix? (see above example; no trailing slash) http://openjerseycity.org/pelican
	> Do you want to enable article pagination? (Y/n) 
	> How many articles per page do you want? [10] 
	> Do you want to generate a Fabfile/Makefile to automate generation and publishing? (Y/n) 
	> Do you want an auto-reload & simpleHTTP script to assist with theme and site development? (Y/n) 
	> Do you want to upload your website using FTP? (y/N) 
	> Do you want to upload your website using SSH? (y/N) 
	> Do you want to upload your website using Dropbox? (y/N) 
	> Do you want to upload your website using S3? (y/N) 
	> Do you want to upload your website using Rackspace Cloud Files? (y/N) 
	Done. Your new project is available at /Users/alukasiak/Desktop/pelican

Once you finish answering all the questions, your project will consist of the following hierarchy (except for “pages”, which you can optionally add yourself if you plan to create non-chronological content):

	yourproject/
	├── content
	│   └── (pages)
	├── output
	├── develop_server.sh
	├── fabfile.py
	├── Makefile
	├── pelicanconf.py       # Main settings file
	└── publishconf.py       # Settings to use when ready to publish

Adding content
--------------
The next step is to begin adding content.  Quick overview of the process:

* You will store all the articles in the `content` directory created for you
* You can create subfolders inside content directory to define category for each article
* You can create additional pages like "About" in the pages directory
* You will convert content to HTML
* The converted content can be viewed locally or published to the web

By default, the site will be organized by categories.  The categories are defined by the directory the files are in.  For example, a file /blog/content/Technical/mypost.md, will have a category of Technical.

If you would like to organize your files in other ways where the name of the subfolder would not be a good category name, you can set the setting USE_FOLDER_AS_CATEGORY to False in pelicanconf.py. 

The article itself can be crated using one of the several [lightweight markup language](http://en.wikipedia.org/wiki/Lightweight_markup_language) syntax options:

*  [Markdown](http://daringfireball.net/projects/markdown/)
*  [reStructuredText](http://docutils.sourceforge.net/docs/ref/rst/restructuredtext.html)
*  [AsciiDoc](http://asciidoc.org/)
*  [textile](http://redcloth.org/textile/writing-paragraph-text/)

For Data Gallery, we will use Markdown, a text-to-HTML conversion tool for web writers. “Markdown” is two things: (1) a plain text formatting syntax; and (2) a software tool that converts the plain text formatting to HTML.  The overriding design goal for Markdown’s formatting syntax is to make it as readable as possible.

You will need to install Markdown using pip:

	pip install Markdown

The Markdown file shold end with `.md` suffix.  At the top the file, include, Metadata.  Aside from the title, none of this metadata is mandatory.  

	Title: My super title
	Date: 2010-12-03 10:20
	Tags: thats, awesome
	Category: yeah
	Slug: my-super-post
	Author: Alexis Metaireau
	Summary: Short version for index and feeds

	This is the content of my super blog post.

To create a Markdown file, try this simple on-line [dingus](http://daringfireball.net/projects/markdown/dingus) tool.  The full documentation for Markdown syntax can be found [here](http://daringfireball.net/projects/markdown/syntax).

To add "About" page to the site, create `pages` directory inside `content` directory add about.md Markdown file.

If there is no summary metadata for a given post, the SUMMARY_MAX_LENGTH setting can be used to specify how many words from the beginning of an article are used as the summary.

Editing pelicanconf.py and publishconf.py
-----------------------------------------
The configuration consists of `pelicanconf.py`, which is the main configuration file for your entire site where everything goes, and `publishconf.py` which is used when you are going to deploy your site.  The `pelicanpublish.py` file should only contain the configuration necessary for a production deployment. This includes DISQUS_SITENAME and GOOGLE_ANALYTICS. This is really great as you can keep testing locally without having your Google Analytics stats messed up, or having to keep loading Disqus.  For more info:  http://stackoverflow.com/questions/20817192/what-is-the-difference-between-pelicanconf-and-publishconf-when-using-pelican/#answers.

In `pelicanconf.py`, at minimum update TIMEZONE, LINKS and SOCIAL.

In `pelicanpublish.py`, at minimum update SITEURL and RELATIVE_URLS.  There are two supported methods for URL formation: relative and absolute. Relative URLs are useful when testing locally, and absolute URLs are reliable and most useful when publishing.

Building the site
-----------------
Once you have some content to generate, you can convert it to HTML in your project directory:

	make html

An alternative command to "make html" is `pelican content -s pelicanconf.py`.

The `output` directory is generated by Pelican and can be deleted and regenerated at any time.

Running the site locally
------------------------
To start local web server:

	make serve
 
In your browser, view [http://localhost:8000](http://localhost:8000).

Publishing on GitHub
--------------------
To publish a Pelican site as a GitHub Project Page you will need to push the content of the `output` directory generated by Pelican to a repository’s `gh-pages` branch on GitHub.

Create a new repo called `project`.  Follow [those instructions](https://help.github.com/articles/creating-a-new-repository).

Only the contents of the output repository need to be added to GitHub.  To simplify the process, use "ghp-import", which can be installed with "pip":

	pip ghp-import

To push changes to GitHub run:

	ghp-import output
	git push origin gh-pages

In your browser, view `https://username.github.io/project`.  In case of this project the url is [http://openjerseycity.org/pelican/](http://openjerseycity.org/pelican/).
