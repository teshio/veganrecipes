---
layout: page
title: Recipes
permalink: /recipes/
---
<h1>Recipes</h1>

<p>
<table>
{% assign recipes = site.recipes | sort:"order"%}
{% for r in recipes %}
  <tr>
    <td><a href="{{r.url}}">{{r.title}}</a></td>
    <td>{{ r.description | strip_html | truncatewords: 20 }}</td>
  </tr>
{% endfor %}
</table>
</p>
