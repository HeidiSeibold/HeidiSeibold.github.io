---
layout: page
title: Archive
---

## Blog Posts

{% for post in site.posts %}
* {{ post.date | date_to_string }} &raquo; [ {{ post.title }} ]({{ post.url }})
{% endfor %}

<br/>



## Tags

{% assign rawtags = "" %}
{% for post in site.posts %}
{% assign ttags = post.tags | join:'|' | append:'|' %}
{% assign rawtags = rawtags | append:ttags %}
{% endfor %}

{% assign rawtags = rawtags | split:'|' | sort %}

{% assign tags = "" %}

{% for tag in rawtags %}
{% if tag != "" %}

{% if tags == "" %}
{% assign tags = tag | split:'|' %}
{% endif %}

{% unless tags contains tag %}
{% assign tags = tags | join:'|' | append:'|' | append:tag | split:'|' %}
{% endunless %}
{% endif %}
{% endfor %}


<p>
{% for tag in tags %}
<a href="#{{ tag | slugify }}" class="codinfox-tag-mark"> {{ tag }} </a> &nbsp;&nbsp;
{% endfor %}
</p>

{% for tag in tags %}
<h5 id="{{ tag | slugify }}">{{ tag }}</h5>
<ul class="codinfox-category-list">
{% for post in site.posts %}
{% if post.tags contains tag %}
<li>
<p>
<a href="{{ post.url }}">
{{ post.title }}
<small>{{ post.date | date_to_string }}</small>
</a>
{% for tag in post.tags %}
<a class="codinfox-tag-mark" href="/blog/tag/#{{ tag | slugify }}">{{ tag }}</a>
{% endfor %}
</p>
</li>
{% endif %}
{% endfor %}
</ul>
{% endfor %}





## Categories

{% assign rawcats = "" %}
{% for post in site.posts %}
{% assign tcats = post.category | join:'|' | append:'|' %}
{% assign rawcats = rawcats | append:tcats %}
{% endfor %}

{% assign rawcats = rawcats | split:'|' | sort %}

{% assign cats = "" %}

{% for cat in rawcats %}
{% if cat != "" %}

{% if cats == "" %}
{% assign cats = cat | split:'|' %}
{% endif %}

{% unless cats contains cat %}
{% assign cats = cats | join:'|' | append:'|' | append:cat | split:'|' %}
{% endunless %}
{% endif %}
{% endfor %}

<p>
{% for ct in cats %}
<a href="#{{ ct | slugify }}" class="codinfox-category-mark" style="color:#999;text-decoration: none;"> {{ ct }} </a> &nbsp;&nbsp;
{% endfor %}
<a href="#no-category" class="codinfox-category-mark" style="color:#999;text-decoration: none;"> No Category </a> &nbsp;&nbsp;
</p>

{% for ct in cats %}
<h5 id="{{ ct | slugify }}">{{ ct }}</h5>
<ul class="codinfox-category-list">
{% for post in site.posts %}
{% if post.category contains ct %}
<li>
<p>
<a href="{{ post.url }}">
{{ post.title }}
<small>{{ post.date | date_to_string }}</small>
</a>
{% for tag in post.tags %}
<a class="codinfox-tag-mark" href="/blog/tag/#{{ tag | slugify }}">{{ tag }}</a>
{% endfor %}
</p>
</li>
{% endif %}
{% endfor %}
</ul>
{% endfor %}

<h5 id="no-category">No Category</h5>
<ul class="codinfox-category-list">
{% for post in site.posts %}
{% unless post.category %}
<li>
<p>
<a href="{{ post.url }}">
{{ post.title }}
<small>{{ post.date | date_to_string }}</small>
</a>
{% for tag in post.tags %}
<a class="codinfox-tag-mark" href="/blog/tag/#{{ tag | slugify }}">{{ tag }}</a>
{% endfor %}
</p>
</li>
{% endunless %}
{% endfor %}
</ul>

