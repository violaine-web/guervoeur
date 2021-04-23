---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

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
    <a href="archipel">Ils et Elles, mon archipel</a>
  </li>
</ul>

{% for essai-1 in site.essais-1 %}
  <h2>{{ essai-1.title }}</h2>
  <h3>{{ essai-1.subtitle }}</h3>
  <time datetime="{{ essai-1.date | date_to_xmlschema }}" itemprop="datePublished">
        {% assign date_format = site.minima.date_format | default: "%-d %b %Y" %}
        {% assign date_english = essai-1.date | date: date_format %}
        {% include date-french.html %}
        {{ date_french }}
      </time>
  <p>{{ essai-1.content | markdownify }}</p>
{% endfor %}