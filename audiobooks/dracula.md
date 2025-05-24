---
layout: default
title: Dracula Audiobook
---

<div class="max-w-3xl mx-auto px-4 py-12">
  <h1 class="text-4xl md:text-5xl font-bold text-indigo-700 mb-8">Dracula Audiobook <span class="text-gray-600">(Hebrew)</span></h1>

  <p class="text-lg text-gray-700 mb-6">Listen to the audiobook version of our simplified *Dracula* in Hebrew. Select a track below:</p>

  <div class="grid grid-cols-1 sm:grid-cols-2 gap-6">
    {% assign chapters = "1_1,1_2,1_3,1_4,1_5,2_1,2_2,2_3,2_4,2_5,2_6,3_1,3_2,3_3,3_4,3_5" | split: "," %}
    {% for chapter in chapters %}
    <div class="bg-white shadow-md rounded-lg p-4 border border-gray-200">
      <p class="text-sm text-gray-500 mb-2 font-semibold">Chapter {{ chapter | replace: "_", "." }}</p>
      <audio id="audio-{{ chapter }}" controls preload="auto" class="w-full">
        <source src="/audio/dracula/Dr {{ chapter }}.mp3" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
    </div>
    {% endfor %}
  </div>
</div>
