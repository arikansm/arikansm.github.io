---
layout: homepage
---

{% for post in site.posts %}
	{% if forloop.first == true %}
	 
<div class="w3-row-padding">
<div class="w3-col m12">
<div class="w3-card w3-round w3-white">
<div class="w3-container w3-padding">
<h4>{{ post.title }}</h4>
<hr class="w3-clear">
{{ post.excerpt }}<button onclick="location.href='{{ post.url }}'" class="w3-button  w3-green w3-margin-bottom"><i class="fa fa-book"></i> Devam Et</button>
<span class="w3-right w3-opacity">{{ post.date | date: "%d/%m/%Y" }}</span>
</div>
</div>
</div>
</div>
	{% else %}
	
<div class="w3-container w3-card w3-white w3-round w3-margin"><br>

<h4>{{ post.title }}</h4>
<hr class="w3-clear">
{{ post.excerpt }}
<button onclick="location.href='{{ post.url }}'" class="w3-button  w3-green w3-margin-bottom"><i class="fa fa-book"></i> Devam Et</button>
<span class="w3-right w3-opacity">{{ post.date | date: "%d/%m/%Y" }}</span>
</div>
	
	{% endif %}
{% endfor %}