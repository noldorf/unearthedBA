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
            <article class="archive-item">
            <a href="{{ site.baseurl }}{{ post.url }}"> 
            {% if post.title and post.title != "" %}<h2>{{post.title}}</h2>{% else %}{{post.excerpt |strip_html}}{%endif%}</a>
            <div>
                    {% for category in post.categories %}
                    <a class="post-tags" name="Category {{category}}">{{category}}</a>
                    {% unless forloop.last %}&nbsp;{% endunless %}
                    {% endfor %}
                  </div>
            <div class="entry">{{ post.excerpt }}</div>
            <a href="{{ site.baseurl }}{{ post.url }}" class="read-more">Read More</a>
            </article>
        {% endfor %}
    {%endif%}
  </div>
{% endfor %}
</div>