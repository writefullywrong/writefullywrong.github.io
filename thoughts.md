---
title: /thoughts
layout: page
permalink: thoughts
---

<h1>Thoughts</h1>

> A collection of thoughts on various topics.

<div id="thoughts">
{% for category in site.categories %}
  <div class="category">
    {% capture category_name %}{{ category | first }}{% endcapture %}
    {% if category_name == "on_writing" %}
    <div id="{{ category_name }}">
      {%- assign date_format = "%Y-%m-%d" -%}
      <h2 class="category-title">{{ category_name | replace: '_', ' ' | upcase }}</h2>
      <ul class="category-entry">
      {% for post in site.categories[category_name] %}
        <li>[ {{ post.date | date: date_format }} ] <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>
      {% endfor %}
      </ul>
    </div>
    {% endif %}
  </div>
{% endfor %}
</div>
<div id="thoughts">
{% for category in site.categories %}
  <div class="category">
    {% capture category_name %}{{ category | first }}{% endcapture %}
    {% if category_name == "off_topic" %}
    <div id="{{ category_name }}">
      {%- assign date_format = "%Y-%m-%d" -%}
      <h2 class="category-title">{{ category_name | replace: '_', ' ' | upcase }}</h2>
      <ul class="category-entry">
      {% for post in site.categories[category_name] %}
        <li>[ {{ post.date | date: date_format }} ] <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>
      {% endfor %}
      </ul>
    </div>
    {% endif %}
  </div>
{% endfor %}
</div>
