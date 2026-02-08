---
layout: default
title: BMW DIY Manual
---

<style>
  .guide-container { display: flex; flex-direction: column; gap: 12px; padding: 10px 0; }
  .category-title { 
    font-family: -apple-system, sans-serif;
    border-bottom: 2px solid #eaecef;
    padding-bottom: 8px;
    margin-top: 25px;
    color: #24292e;
  }
  .guide-card {
    display: flex;
    align-items: center;
    padding: 16px;
    background: #ffffff;
    border: 1px solid #e1e4e8;
    border-radius: 10px;
    text-decoration: none !important;
    box-shadow: 0 2px 4px rgba(0,0,0,0.05);
  }
  .guide-card:active { background-color: #f6f8fa; transform: scale(0.98); }
  .icon { font-size: 20px; margin-right: 12px; }
  .guide-name { color: #0366d6; font-weight: 600; }
</style>

# 🛠️ Maintenance Library

{% comment %} 
  Filter for only .html files and exclude any file that lives inside a '_files' folder
{% endcomment %}

<div class="guide-container">
{% for file in site.static_files %}
  {% if file.extname == ".html" %}
    {% unless file.path contains "_files/" %}
      <a href="{{ site.baseurl }}{{ file.path }}" class="guide-card">
        <div class="icon">🔧</div>
        <div class="guide-name">
          {{ file.basename | replace: "_", " " | capitalize }}
        </div>
      </a>
    {% endunless %}
  {% endif %}
{% endfor %}
</div>

---
*Tip: If you're using a phone, rotate to landscape to see larger diagrams in the guides.*
