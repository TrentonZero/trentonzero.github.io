---
layout: page
title: Recent Posts 
tagline: What's new in the land of Vanyanan?
---
{% include JB/setup %}

{% for post in site.posts limit:10 %}
<h2 class="post-title"><a href="{{ post.url }}">{{ post.title }}</a></h2>
<p class="post-meta">{{ post.date | date_to_string }}</p>
<p><img style="width:10em;float:left;margin-right:1em;margin-bottom:1em" src="{{ post.image }}"></img></p>
<p class="post-excerpt">{{ post.excerpt | strip_html }}&hellip; (<a href="{{ post.url }}">Read More</a>)</p>

<!-- this clear:both forces the next post to be below the floating image, if the image is taller than the current post -->
<div style="clear:both">
</div>

{% endfor %}

<h2><a style="margin-top:5em" href="/archive.html"> More TrentonZero</a></h2>
