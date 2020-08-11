---
layout: page
title: Recipes
last_modified_at: 2020-08-11 09:30
permalink: /recipes/
---

<h1>Recipes</h1>

{% assign categories = site.recipe_categories | sort:"category_id"%}
{% assign recipes = site.recipes | sort:"order"%}

{% for c in categories %}
  {% assign category_id = c.category_id %}

  <section>
    <h2>{{c.title}}</h2>

    <p>
    {{c.description}}
    </p>

    <table>
    <thead>
      <tr>
      <th>test</th>
      </tr>
    </thead>

    {% for r in recipes %}
    {% if r.recipe_category_id == category_id %}
      <tr>
        <td>
          {% assign r_url = r.url | prepend: site.baseurl | prepend: site.url %}
          <a href="{{r.url | prepend: site.baseurl | prepend: site.url}}">{{r.title}}</a><br>
          {{ r.description | strip_html | truncatewords: 20 }}
          <a href="{{r_url}}">details</a><br>
        </td>
      </tr>
    {% endif %}
    {% endfor %}
    </table>
  </section>
  {% unless forloop.last %}<hr>{% endunless %}


{% endfor %}
