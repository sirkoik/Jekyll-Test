---
layout: post
title:  "First test post"
date:   2019-02-17 16:09:01 -0500
categories: testing myposts
---

# Hello there!

I'm just testing out Jekyll. I'm glad to finally get it working!

Here are my notes on how to get it working.

1. Install ruby
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
7. If you get an error message related to tzinfo, type the following:  
```bash
bundle update
```
8. Now navigate to `http://0.0.0.0:4000`; should see the site.
10. Now add `.gitignore`s for the vendor and bundle files, so they don't get uploaded (they're only needed so your local computer can run the server)
11. Make sure to set the `_config.yml` `baseurl` to `/<repository-name>/` and add it if it isn't
12. Needs to be on `gh-pages` branch.
```bash
git checkout -b gh-pages  
git add .  
git commit -m 'Add Jekyll'  
git push origin gh-pages
```
15. If remote repository is not created, do so on GitHub website and follow instructions to synch a local repository
