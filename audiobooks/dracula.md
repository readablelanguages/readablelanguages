---
layout: default
title: Dracula Audiobook
---

<div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 py-8">
  <h1 class="text-4xl font-bold text-indigo-800 mb-4">Dracula Audiobook <span class="text-gray-600">(Hebrew)</span></h1>
  <p class="text-md text-gray-600 mb-6 leading-relaxed max-w-prose">
    Listen to selected chapters of Dracula in easy Hebrew, specially adapted for learners.
  </p>

  <!-- Amazon Section -->
  <div class="mb-10 flex flex-col sm:flex-row items-center justify-between gap-4">
    <div class="flex items-center gap-4">
      <img src="/assets/images/dracula_thumbnail.jpg" alt="Dracula Hebrew Cover" class="w-16 h-auto rounded shadow-md">
      <span class="text-lg font-semibold text-gray-700">Get the book on Amazon:</span>
    </div>
    <div class="flex gap-2 items-center">
      <select id="amazon-store-select" class="border border-gray-300 rounded px-3 py-2 text-gray-700">
        <option value="com">Amazon.com</option>
        <option value="co.uk">Amazon UK</option>
        <option value="de">Amazon Germany</option>
        <option value="fr">Amazon France</option>
        <option value="co.jp">Amazon Japan</option>
        <option value="ca">Amazon Canada</option>
        <option value="it">Amazon Italy</option>
        <option value="es">Amazon Spain</option>
        <option value="com.br">Amazon Brazil</option>
        <option value="pl">Amazon Poland</option>
      </select>
      <a id="amazon-link" href="https://www.amazon.com/dp/B0F8J7T6RK" target="_blank"
         class="bg-orange-500 hover:bg-orange-600 text-white font-semibold px-4 py-2 rounded shadow">
        Go to Amazon
      </a>
    </div>
  </div>

  <!-- Audio Section -->
  {% assign chapters = "1_1,1_2,1_3,1_4,1_5,2_1,2_2,2_3,2_4,2_5,2_6,3_1,3_2,3_3,3_4,3_5" | split: "," %}

  <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
    {% for chapter in chapters %}
    <div class="bg-gray-50 border border-gray-200 p-4 rounded-lg shadow hover:shadow-md transition">
      <p class="text-sm text-gray-500 mb-2 font-semibold">Chapter {{ chapter | replace: "_", "." }}</p>
      <audio id="audio-{{ chapter }}" controls preload="auto" class="w-full rounded">
        <source src="/audio/dracula/Dr {{ chapter }}.mp3" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
    </div>
    {% endfor %}
  </div>
</div>

<script>
  const dropdown = document.getElementById('amazon-store-select');
  const link = document.getElementById('amazon-link');
  const asin = 'B0F8J7T6RK';

  dropdown.addEventListener('change', () => {
    const domain = dropdown.value;
    link.href = `https://www.amazon.${domain}/dp/${asin}`;
  });
</script>
