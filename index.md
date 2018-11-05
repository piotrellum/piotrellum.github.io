---
layout: page
title: Piotrellum's personal website
subtitle: Take control of your e-life
use-site-title: true
# css: "/css/
#meta-title: ""
#meta-description: ""
#bigimg:
#  - "/img/big-imgs/costa-rica-house.jpeg" : "Montezuma, Costa Rica (2011)"
---

## News

It is really refreshing to start a  new e-xistence.  Welcome to the e-life of e-lephant Piotrellum, welcome to my site. 


## Blog

<meta property="og:image" content="{{ post.thumbnail }}">
<div class="posts-list">
  {% for post in paginator.posts %}
  <article class="post-preview">
    <a href="{{ post.url | prepend: site.baseurl }}">
	  <h2 class="post-title">{{ post.title }}</h2>
	  {% if post.subtitle %}
	  <h3 class="post-subtitle">
	    {{ post.subtitle }}
	  </h3>
	  {% endif %}
    </a>
    <p class="post-meta">
      Posted on {{ post.date | date: "%B %-d, %Y" }}
    </p>
    <div class="post-entry-container">
      {% if post.image %}
      <div class="post-image">
        <a href="{{ post.url | prepend: site.baseurl }}">
          <img src="{{ post.image }}">
        </a>
      </div>
      {% endif %}
      <div class="post-entry">
        {{ post.excerpt | strip_html | xml_escape | truncatewords: site.excerpt_length }}
        {% assign excerpt_word_count = post.excerpt | number_of_words %}
        {% if post.content != post.excerpt or excerpt_word_count > site.excerpt_length %}
          <a href="{{ post.url | prepend: site.baseurl }}" class="post-read-more">[Read&nbsp;More]</a>
        {% endif %}
      </div>
    </div>
  </article>
  {% endfor %}
</div>