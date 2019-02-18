---
layout: post
title: "Testing GitHub metadata with Jekyll"
date: 2019-02-17 17:51:00
categories: jekyll github
---

The name of this project is {{site.github.project_title}} and is owned by {{site.github.owner_name}}.

Just testing out some metadata variables!

Here are my repositories:
{% for repository in site.github.public_repositories %}
* [{{ repository.name }}]({{ repository.html_url }})
{% endfor %}
