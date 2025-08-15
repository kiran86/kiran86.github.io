---
layout: post
permalink: /certification/
title: certifications
description: 
nav: true
nav_order: 3
---
<ul>
  {% for cert in site.certifications %}
  <li style="margin-bottom: 20px;">
    <a href="{{ cert.link }}" target="_blank">
      <img src="{{ cert.thumbnail }}" alt="{{ cert.short_name }}" style="width: 150px; height: auto; margin-right: 10px; border: 1px solid #ccc;" />
      {{ cert.title | default: cert.short_name }}
    </a>
  </li>
  {% endfor %}
</ul>