---
layout: default
title: Posts
---



<h2 class="category-title">
  <a href="{{ '/posts/ai-shit/' | relative_url }}">
    AI SHIT
  </a>
</h2>
{% assign ai_posts = site.categories["ai-shit"] %}
{% include post-list.html posts=ai_posts %}

<h2 id="finance-shit" class="category-title">
  <a href="#finance-shit">FINANCE SHIT</a>
</h2>
{% assign fin_posts = site.categories["Finance Shit"] %}
{% include post-list.html posts=fin_posts %}

<h2 class="category-title">
  <a href="{{ '/posts/basic-bitch-shit/' | relative_url }}">
    BASIC BITCH SHIT
  </a>
</h2>
{% assign basic_posts = site.categories["basic-bitch-shit"] %}
{% include post-list.html posts=basic_posts %}

<h2 id="other-crap" class="category-title">
  <a href="#other-crap">OTHER CRAP</a>
</h2>
{% assign oth_posts = site.categories["Other Crap"] %}
{% include post-list.html posts=oth_posts %}

