---
layout: default
title: Dracula Audiobook
---

<div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
  <h1 class="text-4xl font-extrabold text-yellow-700 mb-3">Dracula Audiobook <span class="text-gray-600">(Hebrew)</span></h1>
  <p class="text-lg text-gray-700 mb-8 leading-relaxed max-w-prose">
    Listen to selected chapters of <strong>Dracula</strong> in easy Hebrew, specially adapted for learners. The text is available in a simplified Hebrew edition.
  </p>

  <!-- Amazon Section -->
  <div class="mb-12 bg-white p-6 rounded-xl shadow flex flex-col sm:flex-row items-center justify-between gap-6">
    <div class="flex items-center gap-4">
      <img src="/assets/images/dracula_thumbnail.jpg" alt="Dracula Hebrew Cover" class="w-20 h-auto rounded shadow-md">
      <span class="text-lg font-semibold text-gray-800">Get the book on Amazon:</span>
    </div>
    <div class="flex gap-3 items-center">
      <select id="amazon-store-select" class="border border-gray-300 rounded px-3 py-2 text-gray-700 shadow-sm">
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
        <option value="nl">Amazon Netherlands</option>
        <option value="se">Amazon Sweden</option>
        <option value="com.au">Amazon Australia</option>
        <option value="com.mx">Amazon Mexico</option>
        <option value="sg">Amazon Singapore</option>
        <option value="com.tr">Amazon Turkey</option>
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
    <div class="bg-gray-50 border border-gray-200 p-5 rounded-lg shadow hover:shadow-md transition">
      <p class="text-sm text-gray-600 font-medium mb-2">Chapter {{ chapter | replace: "_", "." }}</p>
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
