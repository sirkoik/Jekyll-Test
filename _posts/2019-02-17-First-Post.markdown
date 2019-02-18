---
layout: post
title:  "How to install and run a site with Jekyll"
date:   2019-02-17 16:43:01 -0500
categories: testing myposts
---

# Hello there!

Here are my notes on how to get Jekyll working.  
1. Install Ruby
2. Install the bundler dependency manager for Ruby.  
```bash
sudo gem install bundler
```
1. Start out with an empty repository.
2. Add the following into a file called Gemfile:  
```
source 'https://rubygems.org'  
gem 'github-pages'
```
3. Run:  
```bash
bundle install --path .vendor/bundle --jobs 4
```
4. make sure Jekyll was correctly installed  
```bash
bundle exec jekyll
```
5. Add boilerplate site files. Put into a dir, then move it into the root dir:  
```bash
bundle exec jekyll new initdir  
mv initdir/{.,}* .  
rmdir initdir
```
6. run the server:  
```bash
bundle exec jekyll serve --watch
```
7. If you get error messages related to tzinfo, type the following:  
```bash
bundle update
```
8. Now navigate to `http://0.0.0.0:4000`; you should see the site.
10. Everything is set up locally. Now add changes to make compatible with the remote repository.
10. Now add `.gitignore`s for the vendor and bundle files, so they don't get uploaded (they're only needed so your local computer can run the server)
11. Make sure to set the `_config.yml` `baseurl` to `/<repository-name>/` and add it if it isn't
12. Needs to be on `gh-pages` branch.
```bash
git checkout -b gh-pages  
git add .  
git commit -m 'Add Jekyll'  
git push origin gh-pages
```
1. If remote repository is not created, do so on GitHub website and follow instructions to synch a local repository
1. Always make edits on the `gh-pages` branch.
1. You can add new posts in the `_posts` directory.
1. If set up properly the `gh-pages` site will accessible in `https://<username>.github.io/<repository-name>`. Might take a few seconds to update
