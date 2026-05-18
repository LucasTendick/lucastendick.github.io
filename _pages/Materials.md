---
layout: page
permalink: /Materials/
title: Materials
description: Here, you can find some slides, videos, and posters of my work from conferences that I attended. A complete list of conferences that I attended can be found in my CV.
nav: true
nav_order: 4
calendar: false
---



<div class="news">
  {% if site.talks  %}
    <div class="table-responsive">
      <table class="table table-sm table-borderless">
      {% assign news = site.talks | reverse %}
      {% for item in news limit: site.news_limit %}
        <tr>
          <th scope="row">{{ item.date | date: "%b %-d, %Y" }}</th>
          <td>
            {% if item.inline %}
              {{ item.content | remove: '<p>' | remove: '</p>' | emojify }}
            {% else %}
              <a class="news-title" href="{{ item.url | relative_url }}">{{ item.title }}</a>
            {% endif %}
        <td>
        {% if item.place -%} 
            <span class="talks-place">{{ item.place }}</span>
        {%- endif %}
        </td>
          </td>
        </tr>
      {% endfor %}
      </table>
    </div>
  {% else %}
    <p>No talks so far...</p>
  {% endif %}
</div>
