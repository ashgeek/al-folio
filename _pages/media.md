---
layout: page
title: media
permalink: /media/
description: Blockchain times were good.
nav: true
---

<div class="projects grid">

  {% assign sorted_media = site.media | sort: "importance" %}
  {% for media in sorted_media %}
  <div class="grid-item">
    {% if media.redirect %}
    <a href="{{ media.redirect }}" target="_blank">
    {% else %}
    <a href="{{ media.url | relative_url }}">
    {% endif %}
      <div class="card hoverable">
        {% if media.img %}
        <img src="{{ media.img | relative_url }}" alt="media thumbnail">
        {% endif %}
        <div class="card-body">
          <h2 class="card-title text-lowercase">{{ media.title }}</h2>
          <p class="card-text">{{ media.description }}</p>
          <div class="row ml-1 mr-1 p-0">
            {% if media.github %}
            <div class="github-icon">
              <div class="icon" data-toggle="tooltip" title="Code Repository">
                <a href="{{ media.github }}" target="_blank"><i class="fab fa-github gh-icon"></i></a>
              </div>
              {% if media.github_stars %}
              <span class="stars" data-toggle="tooltip" title="GitHub Stars">
                <i class="fas fa-star"></i>
                <span id="{{ media.github_stars }}-stars"></span>
              </span>
              {% endif %}
            </div>
            {% endif %}
          </div>
        </div>
      </div>
    </a>
  </div>
{% endfor %}

</div>