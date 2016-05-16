---
title: Accessibility
description: Voluntary Product Accessibility Template (VPAT) outlining §508 accessibility information
permalink: /accessibility/
layout: default
redirect_from:
  - /508/
  - /vpat/
---

{{ page.description }}
{: .lead }

<h3 id="summary">Summary</h3>
<table class="table table-striped table-bordered table-condensed accessibility">
  <tr>
    <th>Section</th>
    <th>Title</th>
    <th>Level of support</th>
    <th>Remarks and explanations</th>
  </tr>
  {% for section in site.data.accessibility.sections %}
    {% assign section_number   = section[0] %}
    {% assign section_title    = section[1].title %}
    {% assign section_support  = section[1].support %}
    {% assign section_comments = section[1].comments %}
    <tr>
      <td class="subsection">§ {{ section_number }}</a></td>
      <td><a href="#{{ section_title | slugify }}">{{ section_title }}</a></td>
      <td>{{ section_support }}</td>
      <td>{{ section_comments }}</td>
    </tr>
  {% endfor %}
</table>

{% for section in site.data.accessibility.sections %}
  {% assign section_number   = section[0] %}
  {% assign section_title    = section[1].title %}
  {% assign section_criteria = section[1].criteria %}

  <h3 id="{{ section_title | slugify }}">§ {{ section_number}} - {{ section_title}}</h3>
  <table class="table table-striped table-bordered table-condensed accessibility">
    <tr>
      <th>Subsection</th>
      <th>Criteria</th>
      <th>Level of support</th>
      <th>Remarks and explanations</th>
    </tr>
    {% for criterion in section_criteria %}
      {% assign subsection  = criterion[0] %}
      {% assign requirement = criterion[1].requirement %}
      {% assign support     = criterion[1].support %}
      {% assign comments    = criterion[1].comments %}

      {% comment %} custom logic to format criteria with sub-criteria {% endcomment %}
      {% assign size = subsection | size %}
      {% if size == 2 %}
        {% assign parts = subsection | split:"" %}
        {% assign subsection = parts[0] | append: ")" | append: "(" | append: parts[1] %}
      {% endif %}
      {% comment %} end custom logic {% endcomment %}

      <tr>
        <td class="subsection">§ {{ section_number }}({{ subsection }})</td>
        <td class="criterion">{{ requirement }}</td>
        <td class="support {{ support | slugify }}">{{ support }}</td>
        <td class="comments">{{ comments }}</td>
      </tr>
    {% endfor %}
  </table>
{% endfor %}
