---
layout: page
permalink: /certifications/
title: certifications
description: 
nav: true
nav_order: 3
---
{% assign certs = site.certifications | sort: "date" | reverse %}
<div class="container">
  {% for cert in certs %}
    <div class="card mb-3" style="max-width: 640px;">
      <div class="row g-0">
        <div class="col-md-4 d-flex align-items-center justify-content-center">
          <a href="{{ cert.link }}" target="_blank">
            <img src="{{ cert.thumbnail }}" alt="{{ cert.title }}" class="img-fluid rounded-start" style="max-width: 90%; max-height: 140px;">
          </a>
        </div>
        <div class="col-md-8">
          <div class="card-body">
            <h5 class="card-title mb-2">
              <a href="{{ cert.link }}" target="_blank">{{ cert.title }}</a>
            </h5>
            {% if cert.issuer %}
              <div class="mb-1 text-muted">{{ cert.issuer }}</div>
            {% endif %}
            <p class="card-text">{{ cert.description }}</p>
            <p class="card-text"><small class="text-body-secondary">{{ cert.date | date: "%d-%m-%Y" }}</small></p>
            {% if cert.tags %}
              <div class="mt-3">
                {% for skill in cert.skills %}
                  <span class="badge bg-info text-dark mx-1">{{ skill }}</span>
                {% endfor %}
              </div>
            {% endif %}
          </div>
        </div>
      </div>
    </div>
  {% endfor %}
</div>
