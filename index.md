---
layout: default
---

This development blog details the production of Klinik, a cross-platform suite of audio synthesis and effects tools, with occasional detours into experimental production techniques and reviews of relevant research papers. Music can be found [here](/trax).

# Recent Posts

<ul>
{% for post in site.posts %}
  <li>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    <span>{{ post.date | date_to_string }}</span>
  </li>
{% endfor %}
</ul>