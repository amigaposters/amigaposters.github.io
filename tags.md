---
layout: page
title: Tags
description:  List of all posts organized by tags.
permalink: /tags/
---

<div class="article">
{% for tag in site.tags %}
    {% capture tag_name %}{{ tag | first }}{% endcapture %}
	    <div id="{{ tag_name }}"></div>
        <h3 class="category-head">#{{ tag_name }}</h3>
        <ul>
        {% for post in site.tags[tag_name] %}
        <!-- <div class="article"> -->
            <li>
                <a class="clearlink" href="{{ post.url | relative_url }}">
                    <b>{{ post.title }}</b>
                </a>
                <div class="read-more clearfix">
                    <div class="more-left left">
                        <span class="date"><time>{{ post.date | date: '%B %d, %Y' }}</time></span>
                        <span>categories:&nbsp;</span> 
{% for category in site.categories %}
    {% for npost in category[1] %}
        {% if npost.url == post.url %}
            <span class="posted-in"><a href='/categories/#{{category[0]}}'>{{category[0]}}</a></span>
        {% endif %}
	{% endfor %}
{% endfor %}
                    </div>
                </div>
            </li>
        {% endfor %}
        </ul>
{% endfor %}
</div>
