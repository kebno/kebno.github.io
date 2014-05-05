---
layout: default
---

<h1><a href="/">John K. Boyle</a></h1>
Hi, I'm a graduate research assistant studying ocean acoustics
at Portland State University.

I am part of the [Northwest Electromagnetics and Acoustics Research Laboratory](http://nearlab.ece.pdx.edu).

In my spare time, I work on software and hardware for the [Portland State Aerospace Society](http://psas.pdx.edu).

----------

## Blog Posts
<ul class="posts">
{% for post in site.posts %}
<li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}
</ul>

## Current Projects
* [PSAS Launch Tower Comm](http://github.com/psas/launch-tower-comm)

## Past Projects
* [2013 National Acoustic Beamformer Building Month](/nabebimo.html)

