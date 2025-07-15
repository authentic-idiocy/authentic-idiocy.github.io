---
layout: default
title: Posts
---

<h2 class="category-title">AI SHIT</h2>
{% assign ai_posts = site.categories["AI Shit"] %}
{% include post-list.html posts=ai_posts %}

<h2 class="category-title">FINANCE SHIT</h2>
{% assign fin_posts = site.categories["Finance Shit"] %}
{% include post-list.html posts=fin_posts %}

<h2 class="category-title">BASIC BITCH SHIT</h2>
{% assign basic_posts = site.categories["Basic Bitch Shit"] %}
{% include post-list.html posts=basic_posts %}

<h2 class="category-title">OTHER CRAP</h2>
{% assign oth_posts = site.categories["Other Crap"] %}
{% include post-list.html posts=oth_posts %}
