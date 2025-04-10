---
layout: default
---

This development blog details the production of Klinik, a cross-platform suite of audio synthesis and effects tools, with occasional detours into experimental production techniques and reviews of relevant research papers.

Trax here:

[soundcloud.com/bennywoo](https://www.soundcloud.com/bennywoo) (hyper-romance/electronica)

[soundcloud.com/xep-0076](https://www.soundcloud.com/xep-0076) (rave)

[soundcloud.com/mapsystems](https://www.soundcloud.com/mapsystems) (electracoustic/concrète)

# Recent Posts

<ul>
{% for post in site.posts %}
  <li>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    <span>{{ post.date | date_to_string }}</span>
  </li>
{% endfor %}
</ul>