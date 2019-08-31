---
title: /writings
layout: page
permalink: writings
---
<h1>Writings</h1>
<center><h2>Ongoing Series</h2></center>
<div id="series">
{% for category in site.categories %}
  <div id="category">
    {% capture category_name %}{{ category | first }}{% endcapture %}
      {% if category_name == "series_title" %}
        <div id="{{ category_name }}">
          <strong class="category-title">{{ category_name | replace: '_', ' ' | upcase }}</strong> - Chapters:  
          {% for post in site.categories[category_name] reversed %}
            <a class="chapter" href="{{ site.baseurl }}{{ post.url }}">{% if post.series != nil %}[{{ post.chapter}}]{% else %}{{ post.title }}{% endif %}</a>
          {% endfor %}
        </div>
        <div id="Description">
          <blockquote>Description of story here! </blockquote>
        </div>
      {% endif %}
</div>
{% endfor %}
</div>
<center><h2>Short Stories and One Shots</h2></center>
<div id="prompts">
{% for category in site.categories %}
  <div id="category">
    {% capture category_name %}{{ category | first }}{% endcapture %}
    {% if category_name == "prompts" %}
    <div id="{{ category_name }}">
      <h2 class="category-title">/r/WritingPromts Responses</h2>
      <ul class="category-entry">
      {% for post in site.categories[category_name] reversed %}
        <li><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>
      {% endfor %}
      </ul>
    </div>
    {% endif %}
  </div>
{% endfor %}
</div>
<div id="shorts">
{% for category in site.categories %}
  <div id="category">
    {% capture category_name %}{{ category | first }}{% endcapture %}
    {% if category_name == "shorts" %}
    <div id="{{ category_name }}">
      <h2 class="category-title">Other Short Stories</h2>
      <ul class="category-entry">
      {% for post in site.categories[category_name] reversed %}
        <li><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>
      {% endfor %}
      </ul>
    </div>
    {% endif %}
  </div>
{% endfor %}
</div>
