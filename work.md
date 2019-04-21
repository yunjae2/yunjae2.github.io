---
layout: page
permalink: /work/
title: work 
description: My projects and publications
---

<ul class="post-list">
{% for work in site.work reversed %}
    <li>
        <h2><a class="work-title" href="{{ work.url | prepend: site.baseurl }}" style="line-height:1">{{ work.title }}</a></h2>
        <p class="post-meta">{{ work.date | date: '%B %-d, %Y' }}</p>
      </li>
{% endfor %}
</ul>
