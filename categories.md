---
layout: page
title: Categories
description:  List of all posts organized by categories.
permalink: /categories/
---

<div class="article">
{% for category in site.categories %}
    {% capture category_name %}{{ category | first }}{% endcapture %}
	    <div id="{{ category_name }}"></div>
        <h3 class="category-head">{{ category_name }} ({{site.categories[category_name].size}} posts)</h3>
        <ul>
        {% for post in site.categories[category_name] %}
        <!-- <div class="article"> -->
            <li>
                <a class="clearlink" href="{{ post.url | relative_url }}">
                    <b>{{ post.title }}</b>
                </a>
                <div class="read-more clearfix">
                    <div class="more-left left">
                        <span class="date"><time>{{ post.date | date: '%B %d, %Y' }}</time></span>
						{% if post.tags.size > 0 %}
                        <span>tags:&nbsp;</span> 
                        {% for tag_item in post.tags %}
                        <span class="posted-in"><a href='/tags/#{{tag_item}}'>{{tag_item}}</a></span>
                        {% endfor %}
						{% endif %}
                    </div>
                </div>
            </li>
        <!-- </div> -->
        {% endfor %}
        </ul>
{% endfor %}
</div>
