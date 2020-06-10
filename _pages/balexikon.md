---
layout: page
permalink: /balexikon/
title: BA Lexikon
---

<div id="archives">
{% for category in site.categories %}
  <div class="archive-group">
    {% capture category_name %}{{ category | first }}{% endcapture %}
    {% if category_name == "BA Lexikon" %}
        {% for post in site.categories[category_name] %}
            <article class="archive-item">
            <a href="{{ site.baseurl }}{{ post.url }}"> 
            {% if post.title and post.title != "" %}<h2>{{post.title}}</h2>{% else %}{{post.excerpt |strip_html}}{%endif%}</a>
            <div class="entry">{{ post.excerpt }}</div>
            <a href="{{ site.baseurl }}{{ post.url }}" class="read-more">Read More</a>
            </article>
        {% endfor %}
    {%endif%}
  </div>
{% endfor %}
</div>