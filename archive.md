---
layout: page
title: Archive
banner_image: sample-banner-image-3.jpg
---

<div class="tags-expo">
<div class="tags-expo-section">

{% for post in site.posts %}
  {% capture currentyear %}{{post.date | date: "%Y"}}{% endcapture %}
  {% if currentyear != year %}
    {% unless forloop.first %}
    </ul>
    {% endunless %}
    <h3>{{ currentyear }}</h3>
    <ul class="tags-expo-posts">
    {% capture year %}{{currentyear}}{% endcapture %} 
  {% endif %}

  <a class="post-title" href="{{ site.baseurl }}{{ post.url }}">
    <li>
      {{ post.title }}
      <small class="post-date">{{ post.date | date_to_string }}</small>
    </li>
  </a>

  {% if forloop.last %}
    </ul>
  {% endif %}
{% endfor %}

</div>
</div>
