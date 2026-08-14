---
layout: default
title: Writing
permalink: /writing/
---

# Writing

<!--
  TODO: This lists everything in the "stories" collection (see _stories/),
  grouped by the `category` front-matter field into the sections below. To
  add a new story: copy _stories/example-story.md, rename it, fill in the
  front matter (including `category`), and it'll show up here automatically.
  Categories not in `section_order` are dropped into an "Other" section at
  the end so nothing silently disappears if `category` is left off or typo'd.
-->

{% assign section_order = "Features/Opinions|Breaking News/Live Reporting|Reviews" | split: "|" %}
{% assign all_stories = site.stories | where_exp: "s", "s.published != false" %}

{% for section in section_order %}
  {% assign group = all_stories | where: "category", section | sort: "date" | reverse %}
  {% if group.size > 0 %}
  <h2>{{ section }}</h2>
  <ul class="entry-list">
    {% for story in group %}
    <li>
      <a class="entry-title" href="{{ story.url | relative_url }}">{{ story.title }}</a>
      <span class="entry-meta">
        {% if story.publication %}{{ story.publication }}{% endif %}
      </span>
    </li>
    {% endfor %}
  </ul>
  {% endif %}
{% endfor %}

{% assign leftover = "" | split: "" %}
{% for s in all_stories %}
  {% unless section_order contains s.category %}
    {% assign leftover = leftover | push: s %}
  {% endunless %}
{% endfor %}
{% assign leftover = leftover | sort: "date" | reverse %}
{% if leftover.size > 0 %}
<h2>Other</h2>
<ul class="entry-list">
  {% for story in leftover %}
  <li>
    <a class="entry-title" href="{{ story.url | relative_url }}">{{ story.title }}</a>
    <span class="entry-meta">
      {% if story.publication %}{{ story.publication }}{% endif %}
    </span>
  </li>
  {% endfor %}
</ul>
{% endif %}
