---
layout: page
permalink: /balexicon/
title: BA Lexicon
---
When I started working as a Business Analyst I had to learn so many new concepts and methods. I would like to make it a bit easier for you. That's way I'm collecting here popular terms used in the Business Analyst / Product Manager section. 

If you think a specific term is missing or you have a different understanding of one the terms feel free to reach out via [LinkedIn](https://www.linkedin.com/in/noldorf) or via <a href="mailto:nadine@oldorf.com">email</a>.

---

<div id="archives">
{% for category in site.categories %}
  <div class="archive-group">
    {% capture category_name %}{{ category | first }}{% endcapture %}
    {% if category_name == "BA Lexicon" %}
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