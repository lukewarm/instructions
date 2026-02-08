---
layout: default
title: BMW DIY Manual
---

<style>
  .guide-container {
    display: flex;
    flex-direction: column;
    gap: 15px;
    padding: 10px 0;
  }
  .category-title {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, Arial, sans-serif;
    border-bottom: 2px solid #eaecef;
    padding-bottom: 8px;
    margin-top: 25px;
    color: #24292e;
    font-size: 1.25rem;
  }
  .guide-card {
    display: flex;
    align-items: center;
    padding: 18px;
    background: #ffffff;
    border: 1px solid #e1e4e8;
    border-radius: 12px;
    text-decoration: none !important;
    transition: transform 0.1s, box-shadow 0.1s;
    box-shadow: 0 2px 4px rgba(0,0,0,0.05);
  }
  .guide-card:active {
    transform: scale(0.98);
    background-color: #f6f8fa;
  }
  .icon {
    font-size: 24px;
    margin-right: 15px;
  }
  .guide-info {
    display: flex;
    flex-direction: column;
  }
  .guide-name {
    color: #0366d6;
    font-weight: 600;
    font-size: 1.1rem;
  }
  .guide-meta {
    color: #586069;
    font-size: 0.85rem;
    margin-top: 2px;
  }
</style>

# 🛠️ Maintenance Library

{% assign grouped_files = site.static_files | groupBy_exp: "file", "file.path | split: '/' | slice: 1" %}

{% for group in grouped_files %}
  {% if group.name != "" and group.name != "index.html" %}
    
    <h2 class="category-title">{{ group.name | replace: "_", " " | capitalize }}</h2>
    
    <div class="guide-container">
    {% for file in group.items %}
      {% if file.extname == ".html" %}
        <a href="{{ site.baseurl }}{{ file.path }}" class="guide-card">
          <div class="icon">📄</div>
          <div class="guide-info">
            <span class="guide-name">{{ file.basename | replace: "_", " " | capitalize }}</span>
            <span class="guide-meta">View Instructions</span>
          </div>
        </a>
      {% endif %}
    {% endfor %}
    </div>

  {% endif %}
{% endfor %}

---
*Generated for the garage. Keep it clean!*
