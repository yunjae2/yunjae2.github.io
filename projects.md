---
layout: page
permalink: /projects/
title: projects
---

<ul class="post-list">
{% for project in site.projects reversed %}
    <li>
        <h2><a class="project-title" href="{{ project.url | prepend: site.baseurl }}">{{ project.title }}</a></h2>
        <p class="post-meta">{{ project.start_date | date: '%B, %Y' }} &ndash; {{ project.end_date | date: '%B, %Y' }}</p>
      </li>
{% endfor %}
</ul>
