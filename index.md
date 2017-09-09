---
layout: page
category: blog
---

<ul class="list-posts">
  {% assign empty_category = true %}
  {% for post in site.posts %}
    {% if post.categories contains page.category %}
      <li class="post-teaser">
        <a href="{{ post.url | prepend: site.baseurl }}">
          <span class="post-teaser__title">{{ post.title }}</span>
          <span class="post-teaser__date">{{ post.date | date: "%d/%m/%Y" }}</span>
        </a>
      </li>
      {% assign empty_category = false %}
    {% endif %}
  {% endfor %}

  {% if empty_category %}
    <li class="empty-post-list">
      Parece que no tenemos artículos en esta categoría. Por favor, vuelve a
      la <a href="/">home</a> para ver la lista completa de artículos.
    </li>
  {% endif %}
</ul>

{% include page/explore.html %}
