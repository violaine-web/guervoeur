---
layout: page
---
<ul class="breadcrumb">
  <li class="breadcrumb-item">
    <a href="/index">Guervoeur</a>
  </li>
  <li class="breadcrumb-item">
    <a href="/pages-georgina">Les pages de Georgina</a>
  </li>
  <li class="breadcrumb-item">
    <a href="/petits-recits-zinsenses">Petits récits z'insensés</a>
  </li>
</ul>

{% for essai-2 in site.essais-2 %}
  <h2>{{ essai-2.title }}</h2>
  <h3>{{ essai-2.subtitle }}</h3>
  <time datetime="{{ essai-2.date | date_to_xmlschema }}" itemprop="datePublished">
        {% assign date_format = site.minima.date_format | default: "%-d %b %Y" %}
        {% assign date_english = essai-2.date | date: date_format %}
        {% include date-french.html %}
        {{ date_french }}
      </time>
  <p>{{ essai-2.content | markdownify }}</p>
{% endfor %}