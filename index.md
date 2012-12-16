---
layout: page
title: Home
---
{% include JB/setup %}

<a href="https://github.com/you"><img style="position: absolute; top: 0; left: 0; border: 0;" src="https://s3.amazonaws.com/github/ribbons/forkme_left_green_007200.png" alt="Fork me on GitHub"></a>

Welcome
=======

Currently I am a first-year PhD student in the [Department of Computer
Science & Engineering](http://www.cse.cuhk.edu.hk/) at the [Chinese
University of Hong Kong](http://www.cuhk.edu.hk/). I am a member of the
[Advanced Networking and System Research
Laboratory](http://ansrlab.cse.cuhk.edu.hk/), under the supervision of
[Prof. John C.S. Lui](http://www.cse.cuhk.edu.hk/~cslui/) and
[Prof. Patrick P.C. Lee](http://www.cse.cuhk.edu.hk/~pclee/).

Posts
=====

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

