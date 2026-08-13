---
layout: default
title: Writing
permalink: /writing/
---

# Writing

<!--
  TODO: This lists everything in the "stories" collection (see _stories/).
  To add a new story: copy _stories/_example-story.md, rename it, fill in the
  front matter, and it'll show up here automatically. No need to touch this file.
-->

<ul class="entry-list">
  {% assign stories = site.stories | where_exp: "s", "s.published != false" | sort: "date" | reverse %}
  {% for story in stories %}
  <li>
    <a class="entry-title" href="{{ story.url | relative_url }}">{{ story.title }}</a>
    <span class="entry-meta">
      {% if story.publication %}{{ story.publication }}{% endif %}
      {% if story.date %} · {{ story.date | date: "%B %Y" }}{% endif %}
    </span>
  </li>
  {% endfor %}
</ul>
