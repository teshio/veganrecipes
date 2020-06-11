---
layout: page
---

<p>
<a href="{{ site.url }}{{site.baseurl}}/recipes">back to all recipes</a>
</p>

<h1> {{page.title}}</h1>

<p>
{{page.description}}
</p>

<table>
<thead>
<tr>
<td>Serves</td>
<td>Prep Time</td>
</tr>
</thead>
<tr>
<td>{{page.serves}}</td>
<td>{{page.time}} mins</td>
</tr>
</table>



<h4>Ingredients:</h4>
<ul>
  {% for product in page.ingredients %}
  <li>{{ product.top-level }}
  {% if product.items %}
    <ul>
    {% for item in product.items %}
      <li>{{ item }}</li>
    {% endfor %}
    </ul>
  {% endif %}</li>
  {% endfor %}
</ul>


{{page.content}}
