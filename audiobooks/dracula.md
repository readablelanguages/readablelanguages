---
layout: default
title: Dracula Audiobook
---

# Dracula Audiobook (Hebrew)

{% assign chapters = "1_1,1_2,1_3,1_4,1_5,2_1,2_2,2_3,2_4,2_5,2_6,3_1,3_2,3_3,3_4,3_5" | split: "," %}

{% for chapter in chapters %}
<audio id="audio-{{ chapter }}" controls preload="auto">
  <source src="/audio/dracula/DR {{ chapter }}.mp3" type="audio/mpeg">
  Your browser does not support the audio element.
</audio><br>
{% endfor %}
