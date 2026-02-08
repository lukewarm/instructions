---
layout: default
title: BMW DIY Instructions
---

# 🔧 BMW Maintenance Guides
*Easy-to-follow guides for G20 and G07 maintenance.*

<div style="display: flex; flex-direction: column; gap: 10px;">

{% for file in site.static_files %}
  {% if file.extname == ".html" and file.name != "index.html" %}
    <a href="{{ site.baseurl }}{{ file.path }}" style="
      display: block;
      padding: 15px;
      background: #0366d6;
      color: white;
      text-decoration: none;
      border-radius: 8px;
      text-align: center;
      font-weight: bold;
      font-size: 1.1em;
    ">
      {{ file.basename | replace: "_", " " | capitalize }}
    </a>
  {% endif %}
{% endfor %}

</div>

---
*Tip: Keep your phone in a plastic baggie while working to keep grease off the screen!*
