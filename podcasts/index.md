---
layout: default
title: Podcast Appearances
permalink: /podcasts/
---

# Podcast Appearances

<!--
  TODO: Lists everything in the "appearances" collection (see _appearances/).
  To add one: copy _appearances/example-appearance.md, rename it, fill in the
  front matter — it shows up here automatically.
-->

<ul class="entry-list">
  {% assign appearances = site.appearances | where_exp: "a", "a.published != false" | sort: "date" | reverse %}
  {% for a in appearances %}
  <li>
    <a class="entry-title" href="{{ a.url | relative_url }}">{{ a.title }}</a>
    <span class="entry-meta">
      {% if a.outlet %}{{ a.outlet }}{% endif %}
    </span>
  </li>
  {% endfor %}
</ul>
