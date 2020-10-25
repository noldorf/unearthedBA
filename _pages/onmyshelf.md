---
layout: page
permalink: /onmyshelf/
title: On my Shelf
---

I love to read. I think it is the best way to learn new things, broaden your perspective and I also get most of my inspiration from books. That's why I want to share with you my favorite books here. 

---

<div id="archives">
{% for category in site.categories %}
  <div class="archive-group">
    {% capture category_name %}{{ category | first }}{% endcapture %}
    {% if category_name == "On my Shelf" %}
        {% for post in site.categories[category_name] %}
            <article class="post">
                {% if post.image %}
                    <img class="post-thumbnail" src="{{ post.image }}" />
                {% endif %}
                <div class="post-content">
                    <a href="{{ site.baseurl }}{{ post.url }}"><h1>{{ post.title }}</h1></a>
                    <div class="entry">
                      {{ post.content | strip_html | truncatewords: 15 }}
                      <a href="{{ site.baseurl }}{{ post.url }}" class="read-more">Read More</a>
                    </div>
                    <div>
                      <p class="post_date">{{ post.date | date: "%B %e, %Y" }}</p>
                      {% for category in post.categories %}
                        <a class="post-tags" name="Category {{category}}">{{category}}</a>
                        {% unless forloop.last %}&nbsp;{% endunless %}
                      {% endfor %}
                    </div>
                </div>
            </article>
        {% endfor %}
    {%endif%}
  </div>
{% endfor %}
</div>