OpenJC Blog with Jekyll, hosted on github pages
===============================================

For instructions how to setup a Jekyll blog hosted on github pages, go to this blog: https://help.github.com/articles/using-jekyll-as-a-static-site-generator-with-github-pages/

To create a new post for this Data Gallery blog.
------------
On a terminal, get the source code from github:

`git clone https://github.com/DataGallery/blog`

Build and run the jekyll blog locally:
`cd blog`
`bundle install`
`bundle exec jeckyll serve --baseurl ''`

Then on a brower, 'localhost:4000'

Note that bundle install will create _sites directory and Gemfile.lock file.  You can remove them and rebuild the site.  Never add _sites and Gemfile.loc to github.

To create new post, create a new .md file in the _posts directory and add images in assets directory.  Don't forget to add them to github:

`git add _posts/file.md image.jpg`
`git commit -m "new blog post" _posts/file.md image.jpg`
`git push origin gh-pages`

Check out those editors for markup tips: http://mashable.com/2013/06/24/markdown-tools/

Using the minima theme
-------------- 

This site used https://jekyll.github.io/minima/ theme.


