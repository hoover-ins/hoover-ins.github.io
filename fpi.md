---
layout: page
title: "Fiscal"
permalink: /fpi/
main_nav: true
---
<h1 id="headings">Headings</h1>

<h1>About the Fiscal Policy Initiative</h1>

The Fiscal Policy Initiative researches potential solutions to the nation’s fiscal policy challenges, providing a road map that promotes future economic growth and opportunity. Led by Senior Fellow Joshua D. Rauh, the initiative launched in 2025 with a conference exploring the economic consequences of US fiscal policy trends, including extensive discussions of budget projections, debt sustainability, international responses to debt crises, the effectiveness of government spending and tax policy, and the interaction between fiscal and monetary policies.

<h1>h1. Current Projects</h1>

{% for category in site.categories %}
  {% capture cat %}{{ category | first }}{% endcapture %}
  <h2 id="{{cat}}">{{ cat | capitalize }}</h2>
  {% for desc in site.descriptions %}
    {% if desc.cat == cat %}
      <p class="desc"><em>{{ desc.desc }}</em></p>
    {% endif %}
  {% endfor %}
  <ul class="posts-list">
  {% for post in site.categories[cat] %}
    <li>
      <strong>
        <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
      </strong>
      <span class="post-date">- {{ post.date | date_to_long_string }}</span>
    </li>
  {% endfor %}
  </ul>
  {% if forloop.last == false %}<hr>{% endif %}
{% endfor %}
<br>
