  <h2 style="margin-top: 0;"> Archives </h2>
  <h4 style="margin-top:10%;">This year's posts</h4>
  {%for post in site.posts %}
    {% unless post.next %}
      <ul class="list-unstyled">
    {% else %}
      {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
      {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
      {% if year != nyear %}
        </ul>
        <h3>{{ post.date | date: '%Y' }}</h3>
        <ul class="list-unstyled">
      {% endif %}
    {% endunless %}
      <li style="margin-top:5%;"><a href="{{ post.url }}" style="color:#25aae1;font-size: 125%;">{{ post.title }}</a></li>
  {% endfor %}
  </ul>

