---
layout:     post
title:      How to Use Plugins with Jekyll on Github Pages
date:       2015-06-14 12:00:00
summary:    [Github Pages](http://jekyllrb.com/docs/plugins/) disables custom plugins for security. How can I use them with Jekyll on Github Pages?
categories: Plugins
---

[Github Pages](http://jekyllrb.com/docs/plugins/) disables custom plugins for security. How can I use them with Jekyll on Github Pages?

I wanted to add [lunr.js](https://github.com/slashdotdash/jekyll-lunr-js-search) to this blog, in order to search for keywords quickly.    

Problem:
While you can serve it locally (`jekyll serve`), you cannot push it up to Github Pages with a Gemfile.    

Solution:
1) Make the local build

    jekyll build --watch

This creates a static version of the site in your local directory under _site

2) Copy the directory from _site/ into the Github Pages repo. In this case, it is _site/js:

    cp -r project_root/_site/js project_root/js

Now when you push to the remote Github repo, you will have the JS files that you are looking for with the JS plugin functionality.



