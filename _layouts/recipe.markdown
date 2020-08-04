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

<h4>Method</h4>

{{page.content}}

{% include share.html %}

<p>
<a href="{{ site.url }}{{site.baseurl}}/recipes">back to all recipes</a>
</p>

<div id="disqus_thread"></div>
<script>
  var disqus_config = function () {
    this.page.url = '{{page.url | absolute_url}}';
    this.page.identifier = '{{page.url | absolute_url}}';
  };

  (function() {
    var d = document, s = d.createElement('script');
    s.src = 'https://{{ site.disqus.shortname }}.disqus.com/embed.js';
    s.setAttribute('data-timestamp', +new Date());
    (d.head || d.body).appendChild(s);
  })();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>
